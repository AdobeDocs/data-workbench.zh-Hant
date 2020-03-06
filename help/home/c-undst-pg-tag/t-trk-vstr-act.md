---
description: 使用Flash架構的網站需要特別注意在多媒體內容中擷取訪客動作。
solution: Analytics
title: 追蹤Flash豐富式媒體內容中的訪客活動
topic: Data workbench
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 追蹤Flash豐富式媒體內容中的訪客活動{#tracking-visitor-activity-within-flash-rich-media-content}

使用Flash架構的網站需要特別注意在多媒體內容中擷取訪客動作。

使用 [!DNL Flash] ActionScript，您可以對現有影片進行簡單變更， [!DNL Flash] 以便追蹤所有訪客與影片的互動，例如按鈕點按或滑鼠動作。

若要促進影片中的訪客活動 [!DNL Flash] 追蹤，請遵循下列步驟：

1. 將下列ActionScript程式碼新增至影片。 此程式碼代表您要追蹤之影片中事件可 [!DNL Flash] 呼叫的函式。

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. 建立名為的空白檔 [!DNL flashtag.txt] 案，並將檔案置於您的網頁伺服器上。
1. 在步驟1中的函式中，用檔案位置的完全限定或相對路徑替換[!DNL [PATH_TO_WEB_SERVER]]佔位符 [!DNL flashtag.txt] 。 例如：

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. 將下列ActionScript程式碼新增至所有要追蹤的事件。 此程式碼代表用來擷取事件相關資料的函式呼叫：

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   此範例說明on(release)事件的使用；但是，標籤()函式可能會透過您想要追蹤的任何事件來參考，例如on(press)、on(rollover)、on(roullop)或on(keypress)事件。

   [!DNL [PUT_PAGE_NAME_HERE]]佔位符應替換為表示要跟蹤的頁面或事件的名稱的字串。 [!DNL [PUT_PAGE_NAME_HERE]]變數可手動修改，也可通過變數引用修改，以表示應用程式中頁面或事件的唯一 [!DNL Flash] 名稱。 取代[!DNL [PUT_PAGE_NAME_HERE]]佔位符的值可由簡單名稱組成，也可以構造為表示與完整URI類似的層次結構。 例如：

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe建議您在程式碼部署之前，先編譯頁面名稱和事件名稱的書面規格，以便協調業務需求和開發工作，並降低額外開發週期的可能性。

1. 視需要，可收集其他變數，並與影片中的頁面或事件建立關 [!DNL Flash] 聯。 要執行此操作，請用一組名稱=值對替換[!DNL [PUT_ADDITIONAL_VAR_HERE]]佔位符，這些對由&amp;符號(&amp;)分隔。 例如：

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   可手動或透過變數參考修改變數，以表示要收集的其他屬性以及與頁面或事件相關聯。 如果沒有可收集的其他變數，請刪除[!DNL [PUT_ADDITIONAL_VAR_HERE]]。

   您在豐富式媒體內容中的訪 [!DNL Flash] 客追蹤設定現已完成。 調用事件時，將調用標 [!DNL (PAGENAME,VARIABLES)] 記函式，導致對以下檔案發出HTTP請求。 除了可能觸發的其他函式（如影片中所定義）外，還會呼叫此函 [!DNL Flash] 數：

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

由標籤ActionScript函式產生的 [!DNL Flash] HTTP要求會針對影片中的每個事件收集下列資 [!DNL Flash] 訊。 表格中的最後一列(W3C Name cs-uri-query)代表您函式呼叫中指定之其他變數所收集到的資訊。

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
   <td colname="col2"> 追蹤識別碼（獨特訪客） </td> 
   <td colname="col3"> 訪客初次要求時的感測器從使用者瀏覽器中 <span class="wintitle"> Cookie </span> 讀取的識別碼 </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期 </p> <p>時間 </p> </td> 
   <td colname="col2"> 時間戳記 </td> 
   <td colname="col3"> 伺服器處理請求的時間(精度為100ns;準確性取決於伺服器環境和NTP) </td> 
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
   <td colname="col3"> 由伺服器生成的數字代碼，該代碼記錄HTTP伺服器響應的狀態 </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI莖 </td> 
   <td colname="col3"> 客戶請求的URI的幹部 </td> 
   <td colname="col4"> /flashtag/flashtag.txt </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> 用戶端IP </td> 
   <td colname="col3"> 請求客戶機的IP地址 </td> 
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
   <td colname="col3"> 用於向HTTP伺服器請求的設備 </td> 
   <td colname="col4"> Mozilla/4.0+(相容；+MSIE+6.0;+Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> 來自網域的用戶端Cookie </td> 
   <td colname="col3"> 網站所有使用者Cookie的內容 </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> 查詢字串 </td> 
   <td colname="col3"> 客戶機請求的URI的查詢字串部分（如果有） </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>

