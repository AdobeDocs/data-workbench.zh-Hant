---
description: 使用Flash架構的網站，在擷取多媒體內容中執行的訪客動作時，需要特別注意。
title: 追蹤 Flash 多媒體內容中的訪客活動
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 5%

---

# 追蹤 Flash 多媒體內容中的訪客活動{#tracking-visitor-activity-within-flash-rich-media-content}

使用Flash架構的網站，在擷取多媒體內容中執行的訪客動作時，需要特別注意。

使用[!DNL Flash]ActionScript，您可以對現有的[!DNL Flash]影片進行簡單的變更，以追蹤與影片的所有訪客互動，例如按鈕點按或滑鼠動作。

若要促進[!DNL Flash]影片中的訪客活動追蹤，請遵循下列步驟：

1. 將下列ActionScript程式碼新增至您的影片。 此代碼表示一個函式，可由您要追蹤之[!DNL Flash]影片中的事件呼叫。

   ```
   // FLASH TAG CODE BEGIN
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt";
   function tag(PAGENAME,VARIABLES) {
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0);
   }
   // FLASH TAG CODE END
   ```

1. 建立名為[!DNL flashtag.txt]的空白檔案，並將該檔案放置在Web伺服器上。
1. 在步驟1的函式中，以[!DNL flashtag.txt]檔案位置的完全限定或相對路徑取代\[[!DNL PATH_TO_WEB_SERVER]\]預留位置。 例如：

   ```
   var FLASHTAGURI = https://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. 將下列ActionScript程式碼新增至所有要追蹤的事件。 此程式碼代表用來擷取事件相關資料的函式呼叫：

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   此範例說明on(release)事件的使用方式；不過，標籤()函式可能會透過您要追蹤的任何事件來參照，例如on(press)、on(rollove)、on(rollove)或on(keypress)事件。

   應以字串取代\[[!DNL PUT_PAGE_NAME_HERE]\]預留位置，該字串代表您要追蹤的頁面或事件名稱。 可手動修改\[[!DNL PUT_PAGE_NAME_HERE]\]變數，或透過變數參考修改變數，以表示[!DNL Flash]應用程式中頁面或事件的唯一名稱。 替換\[[!DNL PUT_PAGE_NAME_HERE]\]佔位符的值可能由簡單名稱組成，或者可以結構化為表示類似於完整URI的層次結構。 例如：

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe建議，在代碼部署之前，您應編譯有關頁面名稱和事件名稱的書面規範，以便協調業務需求和開發任務，並減少可能出現的額外開發週期。

1. 如果需要，可以收集其他變數，並將其與[!DNL Flash]影片中的頁面或事件相關聯。 若要這麼做，請以一組名稱=值配對取代\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]預留位置，並以&amp;符號分隔。 例如：

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   您可以手動或透過變數參考來修改變數，以表示要收集並與頁面或事件相關聯的其他屬性。 如果沒有可收集的其他可用變數，請移除\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]。

   [!DNL Flash]多媒體內容中的訪客追蹤設定現已完成。 叫用事件時，將會呼叫標籤[!DNL (PAGENAME,VARIABLES)]函式，導致對下列檔案提出HTTP要求。 除了可依照[!DNL Flash]影片中的定義觸發的其他函式外，還會呼叫此函式：

   ```
   https://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

由[!DNL Flash]標籤ActionScript函式產生的HTTP要求會導致針對[!DNL Flash]影片內的每個事件收集下列資訊。 表格中的最後一列（W3C名稱cs-uri-query）代表針對函式呼叫中指定的其他變數所收集的資訊。

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C名稱 </th>
   <th colname="col2" class="entry"> 收集的資料 </th>
   <th colname="col3" class="entry"> 解釋 </th>
   <th colname="col4" class="entry"> 範例 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> 追蹤識別碼（不重複訪客） </td>
   <td colname="col3"> 訪客初始請求時， <span class="wintitle">感測器</span>從使用者瀏覽器中放置的Cookie讀取的識別碼 </td>
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td>
  </tr>
  <tr>
   <td colname="col1"> <p>日期 </p> <p>時間 </p> </td>
   <td colname="col2"> 時間戳記 </td>
   <td colname="col3"> 伺服器處理請求的時間(精度為100ns;正確性取決於伺服器環境和NTP) </td>
   <td colname="col4"> 2002-11-21 17:21:45.123 </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> 內容類型 </td>
   <td colname="col3"> 從伺服器返回的對象類型 </td>
   <td colname="col4"> 文字/html </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> HTTP回應狀態代碼 </td>
   <td colname="col3"> 由伺服器產生的數值代碼，用於記錄HTTP伺服器回應的狀態 </td>
   <td colname="col4"> 200 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI主體 </td>
   <td colname="col3"> 客戶端請求的URI的幹部 </td>
   <td colname="col4"> /flashtag/flashtag.txt </td>
  </tr>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> 客戶端IP </td>
   <td colname="col3"> 請求客戶端的IP地址 </td>
   <td colname="col4"> 127.0.0.1 </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> 伺服器域名 </td>
   <td colname="col3"> 處理請求的Web伺服器的域名 </td>
   <td colname="col4"> www.mysite.com </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> 反向連結 URL </td>
   <td colname="col3"> 用戶端傳送的HTTP反向連結欄位內容 </td>
   <td colname="col4"></td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> 使用者代理 </td>
   <td colname="col3"> 用於向HTTP伺服器發出請求的設備 </td>
   <td colname="col4"> Mozilla/4.0+(相容；+MSIE+6.0;+Windows+NT+5.1) </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> 來自網域的用戶端Cookie </td>
   <td colname="col3"> 網站上所有使用者Cookie的內容 </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> 查詢字串 </td>
   <td colname="col3"> 客戶端請求的URI的查詢字串部分（如果有） </td>
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td>
  </tr>
 </tbody>
</table>
