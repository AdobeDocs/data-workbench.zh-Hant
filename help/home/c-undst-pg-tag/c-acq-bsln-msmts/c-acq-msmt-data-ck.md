---
description: 在收集的「基線測量」資料中，感測器會收集從訪客機器傳送的網域Cookie，並從您的網站伺服器提出請求。
title: 透過 Cookie 取得測量資料
uuid: 34cd6baf-6317-4774-8165-58208698b53c
exl-id: 37c7b5f6-33bf-4373-963a-e08a826e05df
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 2%

---

# 透過 Cookie 取得測量資料{#acquiring-measurement-data-through-cookies}

在收集的「基線測量」資料中，感測器會收集從訪客機器傳送的網域Cookie，並從您的網站伺服器提出請求。

這包括您的網站在訪客與您的系統互動時設定的永久性和工作階段Cookie。

在大多數情況下，網站會設定永久性Cookie來識別訪客或擷取使用者輸入，以便用於後續的訪客作業。 任何寫入並儲存在永久性Cookie中的資訊，都可與資料工作台伺服器內所有其他測量資料一起擷取及使用。

此類永久性Cookie的範例可能涉及客戶識別碼，其形式為位於訪客機器上之網域特定Cookie內的數值金鑰。 除了將使用者識別為回訪訪客外，還可使用永久性Cookie進一步將訪客識別為舊客，或將訪客系結至客戶資料庫內的資訊，讓離線客戶人口統計資訊顯示在[!DNL Site]中，並用於互動式分析。

工作階段Cookie是透過表單欄位或網站內其他動態互動元素收集使用者輸入的好機制。 如果網站實作表單以擷取使用者特定的輸入資料，則只有在作業作用中時，資訊才會保留在作業Cookie中。 當使用者離開您的網站或隨後結束工作階段時，這些資訊不再儲存在使用者的電腦上。 但是，輸入的資訊由[!DNL Sensor]捕獲，並作為[!DNL Site]內的測量資料提供。

以下是使用工作階段Cookie擷取訪客輸入之單一表單變數的範例。

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

在此範例中，會呼叫函式，以在訪客的機器上設定作業Cookie，其中包含欄位名稱和在表單欄位中輸入的值。 提交表單並請求後續網頁時，作業Cookie集會傳遞至網頁伺服器並由[!DNL Sensor]收集。 因此，資料工作台伺服器中提供下列資料，以用於資料分析：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與v_1 Cookie相關聯的值。 此值代表在表單欄位中輸入的NAME，這會導致設定工作階段Cookie。 | v_1=John Smith |

作業Cookie也可用來反覆擷取HTML頁面記憶體在的表單欄位或多個內嵌JavaScript變數。 在下列範例中，JavaScript可用來遞歸擷取HTML檔案中出現的任何表單欄位，並設定具有適當name=value配對的工作階段Cookie。

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

在此範例中，訪客的機器上會設定工作階段Cookie，其名稱和值為表單內的每個表單欄位。 這包括輸入欄位、核取方塊、選項按鈕、選取方塊和文字區域。 如您在此範例中所注意的，由於表單欄位數目未知，因此必須將所有表單名稱和欄位值擷取為單一字串，並以&amp;符號分隔。 必須執行此步驟，因為使用者在其電腦上的Cookie數量在某一時間點受到限制。 Microsoft Internet Explorer僅允許在開始刪除最舊的Cookie之前存在20個會話Cookie。
