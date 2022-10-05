---
description: Sensor會取得對安裝了Web伺服器的頁面請求(GET請求)中所附的所有測量資料。
title: 取得頁面要求資料
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
exl-id: e42566a3-d5b4-4f1a-b8cd-1ea646041101
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 4%

---

# 取得頁面要求資料{#acquiring-page-request-data}

{{eol}}

Sensor會取得對安裝了Web伺服器的頁面請求(GET請求)中所附的所有測量資料。

[!DNL Sensor] 通過web伺服器的應用程式寫程式介面，直接從web伺服器上運行的web伺服器軟體的實例或實例獲取此測量資料。 [!DNL Sensor] 不訪問web伺服器生成的日誌檔案。 事實上，在 [!DNL Sensor] 而且，Data Workbench伺服器已安裝並測試過後，即可停用Web伺服器的原生記錄功能，而不會影響資料收集。 在許多情況下，禁用將檔案記錄到Web伺服器電腦本身的本地磁碟會提高這些Web伺服器的頁面服務容量，因為將此資訊記錄到Web伺服器電腦的本地磁碟所需的固定磁碟I/O量相對較大。

[!DNL Sensor] 直接從每個web伺服器進程和虛擬web伺服器進程收集測量和web請求資料（如果適用），並將資料臨時寫入web伺服器電腦上的隊列檔案（具有固定磁碟備份的容錯記憶體隊列）。 Sensor傳送器服務（或守護程式，視平台而定）會從佇列檔案中擷取資料，然後壓縮並加密，再將其傳送至Data Workbench伺服器以進行長期儲存。 使用 [!DNL Sensor]，則只有在存在阻止其傳輸的網路或其他問題時，資料才會在隊列檔案中的Web伺服器電腦上累積。 「佇列檔案」可讓您以數小時至數天的有效本機儲存Web請求資料，以在網路或系統故障不允許資料即時傳送至Data Workbench伺服器時保護資料。

[!DNL Sensor] 從每個物理和邏輯Web伺服器進程收集測量資料，按內容類型篩選、壓縮、加密，並將其流式傳輸到data Workbench伺服器。

下表包含 [!DNL Sensor] 未根據 [!DNL Sensor’s] 配置檔案：

<table id="table_5F65474150EC41648B35D0B031FB9B15">
 <thead>
  <tr>
   <th colname="col1" class="entry"> W3C名稱 </th>
   <th colname="col2" class="entry"> 收集的資料 </th>
   <th colname="col3" class="entry"> 解釋 </th>
   <th colname="col4" class="entry"> 解釋 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> 追蹤識別碼（不重複訪客） </td>
   <td colname="col3"> 從使用者瀏覽器中置入之Cookie讀取的識別碼，由 <span class="wintitle"> 感測器 </span> 訪客的初始請求時 </td>
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
   <td colname="col4"> 404 </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> URI主體 </td>
   <td colname="col3"> 客戶端請求的URI的幹部 </td>
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td>
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
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td>
  </tr>
 </tbody>
</table>
