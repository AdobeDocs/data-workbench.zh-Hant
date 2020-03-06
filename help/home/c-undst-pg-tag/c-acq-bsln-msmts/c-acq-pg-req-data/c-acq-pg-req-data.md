---
description: 感測器獲取對已安裝Web伺服器的頁面請求（GET請求）上承載的所有測量資料。
solution: Analytics
title: 取得頁面請求資料
topic: Data workbench
uuid: 06cf2b14-8d2c-483e-8a75-ce772798978f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 取得頁面請求資料{#acquiring-page-request-data}

感測器獲取對已安裝Web伺服器的頁面請求（GET請求）上承載的所有測量資料。

[!DNL Sensor] 直接從您網頁伺服器上執行之網頁伺服器軟體的例項或例項，透過網頁伺服器的應用程式設計介面取得此測量資料。 [!DNL Sensor] 不訪問Web伺服器生成的日誌檔案。 事實上，在安裝 [!DNL Sensor] 並測試資料工作台伺服器後，就可停用Web伺服器的原生記錄功能，而不會影響資料收集。 在很多情況下，禁用將檔案記錄到Web伺服器電腦本身的本地磁碟會提高這些Web伺服器的頁面服務能力，因為將此資訊記錄到Web伺服器電腦的本地磁碟所需的固定磁碟I/O量相對較大。

[!DNL Sensor] 直接從每個Web伺服器進程和虛擬Web伺服器進程收集測量和Web請求資料（如果適用），並將資料臨時寫入Web伺服器機器上的隊列檔案（具有固定磁碟備份的容錯記憶體隊列）。 感測器發射器服務（或守護程式，視平台而定）從隊列檔案中檢索資料，然後壓縮並加密資料，然後再將其傳輸到資料工作台伺服器以進行長期儲存。 使 [!DNL Sensor]用時，只有在網路或其他問題導致無法傳輸資料時，才會將資料儲存在隊列檔案中的Web伺服器電腦上。 佇列檔案可讓數小時至數天的Web請求資料有效地本機儲存，以在網路或系統故障不允許資料即時傳送至資料工作台伺服器時保護資料。

[!DNL Sensor] 收集每個物理和邏輯Web伺服器進程的測量資料，依內容類型進行篩選、壓縮、加密，並將其流式處理到資料工作台伺服器。

下表包含每個未根據配置檔案過濾掉的GET請 [!DNL Sensor] 求所獲取的日誌資訊 [!DNL Sensor’s] 欄位：

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
   <td colname="col2"> 追蹤識別碼（獨特訪客） </td> 
   <td colname="col3"> 訪客初次要求時的感測器從使用者瀏覽器中 <span class="wintitle"> Cookie </span> 讀取的識別碼 </td> 
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
   <td colname="col4"> 404 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI莖 </td> 
   <td colname="col3"> 客戶請求的URI的幹部 </td> 
   <td colname="col4"> <span class="filepath"> pagedir/page.asp </span> </td> 
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
   <td colname="col4"> PAGENAME=dynamic1&amp;link=3001 </td> 
  </tr> 
 </tbody> 
</table>

