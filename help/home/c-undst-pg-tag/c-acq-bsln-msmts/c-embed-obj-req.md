---
description: 在瀏覽器要求頁面的HTML後，瀏覽器會從網頁伺服器要求該頁面HTML中參考的內嵌物件，以填入瀏覽器所顯示的頁面。
solution: Analytics
title: 取得內嵌物件要求 (頁面標記)
topic: Data workbench
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 4%

---


# 取得內嵌物件要求 (頁面標記){#acquiring-embedded-object-requests-page-tags}

在瀏覽器要求頁面的HTML後，瀏覽器會從網頁伺服器要求該頁面HTML中參考的內嵌物件，以填入瀏覽器所顯示的頁面。

這些內嵌物件要求是影像檔或JavaScript檔案最常要求的要求，不過現今網際網路上使用的內嵌物件類型有數百種或數千種。 其中許多內嵌物件要求通常無法用於分析或報告網際網路網站的商業活動；因此，許多此類要求在收購時並不可取，除非它們有特定商業目的，例如展示廣告或對網站活動進行其他測量。

例如，影像可能是廣告，您可能想知道廣告對訪客印象深刻。 JavaScript程式碼片段可用來測量特定瀏覽器具有特定特性，並傳回給擷取 [!DNL Sensor] 用途。 網站上的每個頁面可能有10或100個內嵌物件要求。 如果站點儲存了這些請求中每個請求的日誌資訊，則保持日誌資料可用於未來分析所需的資料儲存量乘以請求的每個頁的嵌入式對象請求數。 因此，您可 [!DNL Site] 以保留對分析很重要的請求，並丟棄其他請求，以免產生不必要的儲存成本。

通過使用內容類型過濾功能中提供的覆蓋功能 [!DNL Sensor]`<image>` （將「Log=1」附加到嵌入對象請求URL的查詢字串），可以獲取該特定嵌入對象請求和相關測量資料，而無需站點管理器儲存該類型的所有請求（例如，所有請求）。

[!DNL Sensor] 在下表中收集由Web伺服器所做的每個內嵌物件要求的測量資料，假設 [!DNL Sensor] 未設定篩選資料或篩選已覆寫。 收集到的資訊會透過x-trackingid或cs(cookie)記錄欄位項目與訪客和工作階段及後續工作階段相關。

<table id="table_11BE08A798E743EC8E76F738F0CE5884"> 
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
   <td colname="col3"> 感測器在初始請求時從用戶瀏覽器中放置的Cookie讀取 <span class="wintitle"> 的 </span> 識別碼 </td> 
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td> 
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
   <td colname="col4"> text/html </td> 
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
   <td colname="col3"> 客戶請求的URI的「stem」部分 </td> 
   <td colname="col4"> pagedir/page.asp </td> 
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
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> 反向連結 URL </td> 
   <td colname="col3"> 用戶端傳送的HTTP反向連結欄位內容 </td> 
   <td colname="col4"> <span class="filepath"> http://www.referringsite.com </span> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> 使用者代理 </td> 
   <td colname="col3"> 用於向HTTP伺服器請求的設備 </td> 
   <td colname="col4"> <p>Mozilla/4.0+(相容；+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> 來自網域的用戶端Cookie </td> 
   <td colname="col3"> 網站所有使用者Cookie的內容 </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x103805878312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> 查詢字串 </td> 
   <td colname="col3"> 客戶機請求的URI的查詢字串部分（如果有） </td> 
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

