---
description: 對於某些網站，必須使用嵌入的對象請求將資訊傳遞到Web伺服器，以便Sensor可以獲取關於實際服務的頁面的詳細資訊，並用於報告和分析。
title: 取得動態頁面名稱
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
exl-id: cd94caf0-b0dc-46c1-8f59-3ebb2f703286
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 1%

---

# 取得動態頁面名稱{#acquiring-dynamic-page-names}

對於某些網站，必須使用嵌入的對象請求將資訊傳遞到Web伺服器，以便Sensor可以獲取關於實際服務的頁面的詳細資訊，並用於報告和分析。

如果頁面的URL（如網頁伺服器所見）不代表瀏覽器所顯示的頁面內容，則此為必要項目。 此情況通常源自於使用個人化或動態內容管理系統，其中頁面中提供的實際內容是透過URL、Cookie、相關資料和應用程式邏輯即時決定。

實作內嵌物件以收集其他測量資料對網站整體效能的影響應降至最低。 Adobe建議您內嵌JavaScript檔案，作為用來收集擴充屬性的物件。 （請注意，JavaScript檔案可內嵌，而不會因使用內嵌影像而對網頁的版面和呈現方式造成任何潛在影響。） 為準確捕獲嵌入對象內傳遞的資訊，Adobe還建議使用通用名稱。 為了命名目的，Adobe將此物件稱為[!DNL zig.js]。 [!DNL zig.js]檔案應建立在安裝[!DNL Sensor]的Web伺服器上的相應目錄內。 此檔案必須存在，要求才不會傳回404錯誤代碼。 檔案本身的內容並不重要。 您應使用名為[!DNL zig.js]的空白檔案，將請求所產生的網路流量減至最少。

若要[!DNL Sensor]收集實際提供頁面的可用名稱，必須將幾行JavaScript程式碼新增至您要追蹤的動態頁面，或您要新增唯一頁面名稱的動態頁面。 此程式碼會在頁面中內嵌JavaScript程式碼片段，導致在頁面載入時向Web伺服器提出第三個內嵌物件要求。 該請求會將已提供之特定頁面的詳細資訊傳送回Web伺服器。 實際提供的頁面名稱會以內嵌物件（在此例中為JavaScript）要求的查詢字串中的變數形式傳回至Web伺服器。

一般而言，內嵌於每個此類HTML頁面的物件要求看起來應如下：

```
<!-- BEGIN REFERENCE PAGE TAG-->
<script language="javascript">
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE
var v = {};
v["_pn"] = "Application Form";
</script>

<script language="javascript" src=”https://www.myserver.com/path/to/zig.js" type="text/javascript"></script>

<noscript>
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/>
</noscript>

<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] 確保記 [!DNL Sensor] 錄要求，儘管內 [!DNL Sensor] 容類型篩選規則相反，例如在儲存JavaScript和影像要求之前先進行篩選。宣告的v_pn變數可識別所提供實際頁面內容的名稱，以便[!DNL Site]知道訪客實際檢視的頁面名稱。 v_pn值可以手動建立，也可以由其他指令碼或應用程式代碼建立。

收集值後，您可以設定Data Workbench伺服器，使用附加至[!DNL zag.gif] URI（例如[!DNL https://www.mysite.com/pageserved.asp?v_pn=Application%20Form]）的查詢字串變數（名稱=值對，例如v_pn=應用程式表單）的內容，作為[!DNL zag.gif] URI的擴充。 除了每個HTTP請求所獲得的基線測量之外，還將利用此請求獲得擴展測量。

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_pn= | 與v_pn查詢字串變數相關聯的值 | v_pn=應用程式表單 |
