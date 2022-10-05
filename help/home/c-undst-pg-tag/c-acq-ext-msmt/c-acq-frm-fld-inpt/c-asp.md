---
description: 網頁通常使用ASP(Active Server Pages)寫程式語言進行結構化。
title: ASP 專屬資訊
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# ASP 專屬資訊{#asp-specific-information}

{{eol}}

網頁通常使用ASP(Active Server Pages)寫程式語言進行結構化。

ASP是一種在IIS（Internet資訊服務）中運行的Microsoft技術。 當瀏覽器請求ASP檔案時，IIS會將請求傳遞給ASP引擎。 ASP引擎逐行讀取ASP檔案，並執行檔案中的指令碼。 最後，ASP檔案以純HTML形式返回到瀏覽器。 ASP提供RESPONDE或REQUEST對象，除了其它用途外，還允許從HTML表單提交的用戶查詢或資料的響應或請求。

在某些情況下，您可能不想將輸入表單的值附加至顯示在使用者瀏覽器之位址列中，或可在HTML程式碼本身中檢視的URL。 簡單的伺服器端JavaScript可讓您將表單欄位名稱及其個別值附加至記錄檔，而無須在使用者的瀏覽器中使用或將它們內嵌至HTML檔案中。 若要擷取在您網站內特定表單中輸入的實際表單值，必須新增幾行程式碼，將表單值附加至記錄請求。

在表單的處理頁面內，納入下列程式碼，將輸入的表單值附加至請求資料（除了將提交的表單值寫入外部資料庫或其他位置之外）:

```
var sName= Request.Form("Name");
var sCity= Request.Form("City");
var sState= Request.Form("State");
var sZip= Request.Form("Zip");

Response.AppendToLog("&v_1=" +  sName);
Response.AppendToLog("&v_2=" +  sCity);
Response.AppendToLog("&v_3=" +  sState);
Response.AppendToLog("&v_4=" +  sZip);
```

此程式會將定義的表單值附加至 [!DNL Form Processing] 頁面。 在記錄資料中，附加的值將可作為 [!DNL Form Processing] 頁面，如下圖所示。 例如， v_1、v_2、v_3和v_4現在將是查詢字串，其中包含輸入到相應表單欄位中的資料。 您可以針對您要擷取的任何其他表單欄位和值複製上述範例中所述的語法。

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您想要擷取每個表單欄位和值並供分析之用，您可以使用下列語法：

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

此範例會取用HTML內顯示的所有表單欄位及其各自的值，並將它們附加為的記錄項目中的查詢字串 [!DNL Form Processing] 頁面。 請注意，這會包含表單中出現的任何隱藏欄位。

日誌資料將如下表詳述：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與NAME查詢字串關聯的值 | v_1=John Smith |
| v_2 | 與CITY查詢字串關聯的值 | v_2=洛杉磯 |
| v_3 | 與STATE查詢字串關聯的值 | v_3=加州 |
| v_4 | 與ZIP查詢字串關聯的值 | v_4=90210 |
