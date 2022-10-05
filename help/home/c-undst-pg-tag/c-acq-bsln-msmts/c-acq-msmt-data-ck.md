---
description: 在收集的基線測量資料中，Sensor會收集從訪客的電腦傳送的網域Cookie（從您的網站伺服器提出請求）。
title: 透過 Cookie 取得測量資料
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# 透過 Cookie 取得測量資料{#acquiring-measurement-data-through-cookies}

{{eol}}

在收集的基線測量資料中，Sensor會收集從訪客的電腦傳送的網域Cookie（從您的網站伺服器提出請求）。

這包括訪客與系統互動時，網站設定的永久性和工作階段Cookie。

在大多數情況下，網站會設定永久性Cookie來識別訪客，或擷取使用者輸入以用於後續的訪客工作階段。 寫入或儲存在永久性Cookie中的任何資訊，都可與Data Workbench伺服器內所有其他測量資料一起擷取及使用。

此類永久性Cookie的範例可能包含客戶識別碼，其形式為位於訪客電腦上之特定網域Cookie內的數值金鑰。 除了將使用者識別為回訪訪客外，永久性Cookie還可用來進一步將訪客識別為回訪客戶，或將訪客與客戶資料庫中包含的資訊系結，以便離線客戶人口統計資訊顯示在 [!DNL Site] 並用於互動式分析。

工作階段Cookie是透過表單欄位或網站內其他動態互動元素收集使用者輸入的良好機制。 若網站實作表單以擷取使用者專屬的輸入資料，則只有工作階段處於作用中狀態，資訊才會保留在工作階段Cookie中。 當使用者離開您的網站或隨後結束工作階段時，資訊不再儲存在使用者的電腦上。 但是，輸入的資訊被 [!DNL Sensor] 可在中作為測量資料使用 [!DNL Site].

以下是使用工作階段Cookie來擷取訪客輸入之單一表單變數的範例。

```
<html> 
<head> 
<title>Cookie Collection </title> 
 
<script language="JavaScript"> 
function AppendFormValues() 
{ 
 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
document.cookie = cookie; 
 
testform.submit(); 
 
} 
</script> 
</head> 
<body> 
<form name="testform" method="post" action="nextpage.asp"> 
<input type="text" size=15 name="name"><br />enter name 
<br><br> 
 
<a href="javascript:AppendFormValues();">Click Here To </a><br /><br /> 
<br /><br /><br /> 
 
</body> 
</html> 
```

在此範例中，會呼叫函式，以在訪客的電腦上以欄位名稱和在表單欄位中輸入的值設定工作階段Cookie。 提交表單並請求後續網頁時，會將工作階段Cookie集傳遞至Web伺服器並收集 [!DNL Sensor]. 因此，Data Workbench伺服器內可使用下列資料，以用於資料分析：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與v_1 Cookie相關聯的值。 此值代表在表單欄位中輸入的NAME，導致工作階段Cookie設定。 | v_1=John Smith |

工作階段Cookie也可用來反覆擷取表單欄位或存在於HTML頁面中的多個內嵌JavaScript變數。 在下列範例中，JavaScript可用來遞回擷取HTML檔案中出現的任何表單欄位，並使用適當的名稱=值配對設定工作階段Cookie。

```
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
var cookie="formcookie="; 
for (i=0; i<document.testform.length; i++){ 
if (document.testform.elements[i].type =="radio") {            
if (document.testform.elements[i].checked){ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
else if (document.testform.elements[i].type =="select") { 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var optionindex = eval(document.testform.elements[i].selectedIndex); 
var formvalue = document.testform.elements[i].options[optionindex].value;             
cookie += formitem + "=" + formvalue + "&"; 
} 
else{ 
var item = document.testform.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
cookie += formitem + "=" + formvalue + "&"; 
} 
} 
document.cookie = cookie; 
document.testform.submit(); 
} 
 
</script>
```

在此範例中，訪客的電腦上會設定工作階段Cookie，其名稱和值包含表單中存在之每個表單欄位。 這包括輸入欄位、核取方塊、選項按鈕、選取方塊和文字區域。 如您在此範例中所注意到，由於表單欄位數目未知，因此必須將所有表單名稱和欄位值擷取為單一字串，並以&amp;符號分隔。 必須執行此步驟，因為使用者在其電腦上某個時間點可能擁有的Cookie數量有限。 Microsoft Internet Explorer只允許20個工作階段Cookie存在，才能開始捨棄最舊的工作階段Cookie。
