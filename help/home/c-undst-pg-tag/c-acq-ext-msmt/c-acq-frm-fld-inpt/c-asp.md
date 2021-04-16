---
description: 網頁通常採用ASP(Active Server Pages)寫程式語言結構。
title: ASP 專屬資訊
uuid: 552288cb-b775-4121-8869-322f2a26932b
exl-id: f73235e1-d44a-4056-b1f4-a86879c19483
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---

# ASP 專屬資訊{#asp-specific-information}

網頁通常採用ASP(Active Server Pages)寫程式語言結構。

ASP是一種在IIS(Internet Information Services)中執行的Microsoft技術。 當瀏覽器要求ASP檔案時，IIS會將要求傳送至ASP引擎。 ASP引擎逐行讀取ASP檔案，並執行檔案中的指令碼。 最後，ASP檔案會以純HTML格式傳回至瀏覽器。 ASP提供RESPONSE或REQUEST物件，除了其他用途外，還允許回應或要求使用者查詢或從HTML表單提交的資料。

在某些情況下，您可能不想將輸入表單的值附加至顯示在使用者瀏覽器位址列中或可在HTML程式碼本身檢視的URL。 簡單的伺服器端JavaScript可讓您將表單欄位名稱及其個別值附加至記錄檔，而不需在使用者的瀏覽器中提供或內嵌至HTML檔案。 若要擷取在網站內特定表單中輸入的實際表單值，必須新增幾行程式碼，才能將表單值附加至記錄請求。

在表單的處理頁面中，請包含下列程式碼，將輸入的表單值附加至請求資料（除了將提交的表單值寫入外部資料庫或其他位置之外）:

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

此程式會將定義的表單值附加至[!DNL Form Processing]頁面的請求資料。 在日誌資料中，附加的值可作為[!DNL Form Processing]頁的查詢字串使用，如下所示。 例如，v_1、v_2、v_3和v_4現在將是查詢字串，包含輸入到適當表單欄位中的資料。 上述範例中所述的語法可針對您想要擷取的任何其他表單欄位和值進行複製。

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

如果您想要擷取每個表單欄位和值並加以分析，可以使用下列語法：

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues); 
```

此示例將採用HTML中顯示的所有表單欄位及其各自的值，並將它們作為查詢字串附加到[!DNL Form Processing]頁的日誌條目中。 請注意，這將包含表單中顯示的任何隱藏欄位。

日誌資料將被增加，如下表中所詳述：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與NAME查詢字串關聯的值 | v_1=John Smith |
| v_2 | 與CITY查詢字串關聯的值 | v_2=洛杉磯 |
| v_3 | 與STATE查詢字串關聯的值 | v_3=加州 |
| v_4 | 與ZIP查詢字串關聯的值 | v_4=90210 |
