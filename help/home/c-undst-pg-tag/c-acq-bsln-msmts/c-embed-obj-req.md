---
description: 瀏覽器請求HTML頁面後，瀏覽器從網頁伺服器請求該頁面HTML中引用的嵌入對象以填充瀏覽器顯示的頁面。
title: 取得內嵌物件要求 (頁面標記)
uuid: 7fe561d1-aa5a-4ac9-82ba-aa27c7d208dd
exl-id: 593e49bc-9619-4e85-8ce3-2e9d23d175c9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 4%

---

# 取得內嵌物件要求 (頁面標記){#acquiring-embedded-object-requests-page-tags}

{{eol}}

瀏覽器請求HTML頁面後，瀏覽器從網頁伺服器請求該頁面HTML中引用的嵌入對象以填充瀏覽器顯示的頁面。

此類嵌入對象請求最常是對影像檔案或JavaScript檔案的請求，儘管當今網際網路上使用的嵌入式對象類型有數百種或可能數千種。 這些嵌入式對象請求中的許多在分析或報告網際網路站點的業務活動時通常沒有用；因此，許多此類請求在收購時並不可取，除非它們具有特定的商業目的，例如展示廣告或對網站活動進行另一種測量。

例如，影像可能是廣告，而您可能想知道廣告是否對訪客留下了深刻印象。 JavaScript程式碼片段可用來進行特定瀏覽器具有特定特性的測量，並傳回至 [!DNL Sensor] 收購。 網站上的每個頁面可能有10或100個內嵌物件要求。 如果站點儲存這些請求中的每個的日誌資訊，則保持日誌資料可用以供將來分析所需的資料儲存量乘以每個請求頁的嵌入式對象請求數。 因此， [!DNL Site] 可讓您保留對分析而言重要的請求，並在產生不必要的儲存成本之前將其他請求捨棄。

使用的內容類型篩選功能中提供的覆寫功能 [!DNL Sensor] （將&quot;Log=1&quot;附加至內嵌物件要求URL的查詢字串），即可取得該特定內嵌物件要求與相關測量資料，而不需要網站管理員儲存該類型的所有要求(例如，所有 `<image>` 要求)。

[!DNL Sensor] 會針對由web伺服器提出的每個內嵌物件要求，收集下表中的測量資料，假設 [!DNL Sensor] 未設定為將其篩選掉，或篩選已覆寫。 收集的資訊會透過x-trackingid或cs(cookie)記錄欄位項目與訪客和工作階段以及後續工作階段相關。

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
   <td colname="col2"> 追蹤識別碼（不重複訪客） </td>
   <td colname="col3"> 從使用者瀏覽器中置入之Cookie讀取的識別碼，由 <span class="wintitle"> 感測器 </span> 初始要求 </td>
   <td colname="col4"> V1st=3C94007B4E01F9C2 </td>
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
   <td colname="col3"> 客戶端請求的URI的「stem」部分 </td>
   <td colname="col4"> pagedir/page.asp </td>
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
   <td colname="col4"> <span class="filepath"> www.domain.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> 反向連結 URL </td>
   <td colname="col3"> 用戶端傳送的HTTP反向連結欄位內容 </td>
   <td colname="col4"> <span class="filepath"> https://www.referringsite.com </span> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> 使用者代理 </td>
   <td colname="col3"> 用於向HTTP伺服器發出請求的設備 </td>
   <td colname="col4"> <p>Mozilla/4.0+(相容；+MSIE+6.0; </p> <p>+Windows+NT+5.1) </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> 來自網域的用戶端Cookie </td>
   <td colname="col3"> 網站上所有使用者Cookie的內容 </td>
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972 x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> 查詢字串 </td>
   <td colname="col3"> 客戶端請求的URI的查詢字串部分（如果有） </td>
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
