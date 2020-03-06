---
description: 對於某些網站，必須使用內嵌物件請求將資訊傳送至Web伺服器，讓Sensor可取得實際提供的頁面詳細資訊，並用於報告和分析。
solution: Analytics
title: 取得動態頁面名稱
topic: Data workbench
uuid: eaa35023-bbfa-4eb9-9ab7-3986187e5537
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 取得動態頁面名稱{#acquiring-dynamic-page-names}

對於某些網站，必須使用內嵌物件請求將資訊傳送至Web伺服器，讓Sensor可取得實際提供的頁面詳細資訊，並用於報告和分析。

如果網頁的URL（如網頁伺服器所見）不代表瀏覽器所顯示的頁面內容，則可能需要此選項。 這種情況通常是由於使用個人化或動態內容管理系統，其中頁面中提供的實際內容是由URL、Cookie、相關資料和應用程式邏輯即時決定。

實作內嵌物件以收集其他測量值，對網站整體效能的影響應降至最低。 Adobe建議您將JavaScript檔案內嵌為用來收集擴充屬性的物件。 （請注意，JavaScript檔案可以內嵌，而不會因使用內嵌影像而對網頁的版面配置和呈現方式造成任何潛在影響。）為了精確擷取內嵌物件內傳遞的資訊，Adobe也建議使用通用名稱。 為了命名目的，Adobe將此物件稱為 [!DNL zig.js]。 應 [!DNL zig.js] 該在安裝的Web伺服器上的相應目錄中 [!DNL Sensor] 建立檔案。 此檔案必須存在，如此請求才不會傳回404錯誤碼。 檔案本身的內容並不重要。 您應使用名為的空白 [!DNL zig.js] 檔案，將因請求而產生的網路流量減到最低。

若 [!DNL Sensor] 要收集實際提供之頁面的可用名稱，必須將幾行JavaScript程式碼新增至您要追蹤或想要新增唯一頁面名稱的動態頁面。 此程式碼會將JavaScript程式碼片段內嵌在頁面中，這會導致在載入頁面時，對網頁伺服器提出第三個內嵌物件要求。 該請求會將已提供之特定頁面的詳細資料傳回至網頁伺服器。 實際提供的頁面名稱會作為內嵌物件（在此例中為JavaScript）要求的查詢字串中的變數，傳回至網頁伺服器。

一般而言，內嵌於每個此類HTML頁面的物件要求應如下：

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

[!DNL Log=1] 確保記 [!DNL Sensor] 錄請求時，即使內容類型篩選規則相 [!DNL Sensor] 反，例如在儲存請求之前先篩選掉JavaScript和影像請求。 宣告的v_pn變數會識別所提供之實際頁面內容的名稱，以便 [!DNL Site] 知道訪客實際檢視的頁面名稱。 v_pn值可以手動建立，也可以由其他指令碼或應用程式碼建立。

收集值後，您可以設定資料工作台伺服器，使用附加至 [!DNL zag.gif] URI(例如， [!DNL http://www.mysite.com/pageserved.asp?v_pn=Application%20Form])的查詢字串變數（name=value對，例如v_pn=Application Form）的內容來擴充 [!DNL zag.gif] URI。 除了每個HTTP請求所獲取的基線測量值外，此請求也會取得延伸測量值。

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_pn= | 與v_pn查詢字串變數相關聯的值 | v_pn=應用程式表單 |

