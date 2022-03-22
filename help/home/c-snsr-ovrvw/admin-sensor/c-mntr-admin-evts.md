---
description: 為了盡快檢測感測器錯誤並在它們導致重大問題或中斷之前對其進行修復，您應定期監視事件日誌。
title: 監視管理事件（感測器）
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 0%

---

# 監控管理事件{#monitoring-administrative-events}

為了盡快檢測感測器錯誤並在它們導致重大問題或中斷之前對其進行修復，您應定期監視事件日誌。

**推薦頻率：** 至少每小時

可以使用Windows事件查看器或Unix Syslog檔案和 [!DNL *.sensor-log] 預設情況下位於 [!DNL Logs] 資料夾 [!DNL Sensor] 安裝目錄。 這些檔案表示在資料收集過程中存在錯誤，尤其是在 [!DNL Sensor] 無法連接到目標 [!DNL data workbench server] 並啟動排隊資料。

## 監視Windows上的事件 {#section-7c0443a356af4381bf22259654f5cd17}

感測器將錯誤記錄到Windows事件查看器的應用程式日誌中，其源為「Adobe」。

根據郵件的嚴重性，郵件記錄為「資訊」、「警告」或「錯誤」。

**開啟Windows事件查看器**:

* 按一下 **開始>控制面板>管理工具>事件查看器**。

## 在Unix上監視事件 {#section-5de3947891fb47ac88b7c855e545d54a}

感測器將錯誤記錄到 [!DNL syslog] 守護程式。

syslog守護程式根據您在syslog.conf檔案中指定的規則將錯誤消息寫入日誌檔案。 根據嚴重性，錯誤記錄時使用標籤&quot;LOG_DAEMON&quot;和&quot;LOG_NOTICE&quot;或&quot;LOG_ERR&quot;。

**開啟Unix系統日誌**

Unix系統日誌通常位於 [!DNL /var/adm/messages] 或 [!DNL /var/log/messages]。

瀏覽到適當位置並開啟系統日誌。

## 瞭解消息格式 {#section-a0899add30fd4b2da58a23b9e3324693}

所有感測器消息都包含字串「感測器」，並按編號以反映所顯示消息的重要性。

| 消息編號 | 消息含義 | 消息字串 |
|---|---|---|
| 1xxx | 資訊 | 感測器資訊# |
| 2xxx | 警告 | 感測器警告# |
| 3xxx | 配置錯誤 | 感測器錯誤號 |
| 4xxx | 操作錯誤 | 感測器錯誤號 |
| 5xxx | 內部錯誤 | 感測器錯誤號 |

>[!NOTE]
>
>警告(2xxx)當前未使用。 這些數字將保留供將來使用。

網路管理工具可設定為每5-10分鐘監視一次消息，以發現「感測器」源的錯誤，並提醒相應人員可能需要干預的問題。 您可以選擇只監視某些類型的事件消息（如「感測器錯誤」字串）的系統。 或者，可以對前面帶「感測器資訊」、「感測器警告」和「感測器錯誤」字串的事件應用不同的規則。

## 識別重要消息 {#section-5a20f5dc18ca4012931d194db855e54e}

在事件日誌中，您應特別注意並立即處理有關隊列大小的任何消息。

例如，消息（如「」） [!DNL Sensor Info 1012: Adobe disk queue is #% full]「需要注意。

## 響應感測器事件消息 {#section-0004c4a169dc4a8882d9bd87dd326ad4}

描述受支援Web伺服器平台的感測器事件和建議操作的表。

**所有平台**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件消息 </th> 
   <th colname="col2" class="entry"> 建議的操作 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 感測器資訊1010:感測器已初始化。 </td> 
   <td colname="col2"> 不需要任何操作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1011:感測器已終止。 排隊的點擊總數## </td> 
   <td colname="col2"> 不需要任何操作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1012:Adobe磁碟隊列已滿#% </td> 
   <td colname="col2"> 每次磁碟隊列利用率超過10%閾值時都記錄此消息。 如果此百分比繼續增長，則應在隊列已滿且資料丟失之前採取操作。 最有可能的問題是感測器已停止與Insight Server通信。 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1013:感測器配置已更改 </td> 
   <td colname="col2"> 不需要任何操作。 感測器檢測到其配置檔案中的更改並將重新載入。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1014:問題種子隨機數生成器 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1016:已載入配置檔案檔案名 </td> 
   <td colname="col2"> 不需要任何操作。 感測器已成功載入列出的配置檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1017:實驗檔案檔案名已載入 </td> 
   <td colname="col2"> 不需要任何操作。 感測器已成功載入列出的實驗檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3016:無法載入配置檔案/mypath/myfile </td> 
   <td colname="col2"> 確認在Web伺服器配置中指定的感測器配置檔案存在，並且具有Web伺服器進程讀取所需的權限。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>感測器3017:無法載入受控實驗配置檔案/mypath/myfile </p> </td> 
   <td colname="col2"> <p>確認txlogd.conf中指定的受控實驗檔案存在，並且txlogd進程具有讀取該檔案所需的權限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3018:無法分析內容篩選器清單。 檢查文本日誌配置檔案 </td> 
   <td colname="col2"> 驗證txlogd.conf中ContentFilterInclude和ContentFilterExclude項的語法。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3023:無法建立鎖(g_lockThrottle) </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3024:無法建立鎖(g_lockConfigCheck) </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4014:無法開啟磁碟隊列。 </td> 
   <td colname="col2"> 驗證txlogd.conf中的QueueFile檔案名，如果認為正確，請與AdobeClientCare聯繫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4020:不是隊列檔案 </td> 
   <td colname="col2"> 驗證txlogd.conf中的QueueFile檔案名，如果認為正確，請與AdobeClientCare聯繫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4021:隊列已滿 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4022:無法映射長度的記憶體塊 &lt;x&gt; 偏移 &lt;y&gt; </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5012:無法建立互斥鎖。 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5013:無法獲取互斥鎖。 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5030:衍生分叉錯誤。 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5031:setsid失敗。 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5032:衍生分叉錯誤。 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5033:chdir失敗。 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5034:已接收信號 </td> 
   <td colname="col2"> 程式可能由外部信號終止。 如果無法確定此信號的源，請與AdobeClientCare聯繫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5035:從外部主調用的退出 </td> 
   <td colname="col2"> 聯繫AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5036:txlogd已在運行 </td> 
   <td colname="col2"> txlogd守護程式的另一個實例已在運行。 如果要運行新實例，請先停止另一個實例。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBMHTTP伺服器**

| 事件消息 | 建議的操作 |
|---|---|
| 感測器錯誤3015:httpd.conf中缺少VisualSciencesConfig指令。 | 這是配置錯誤。 VisualSciencesConfig指令必須位於httpd.conf中，並且參數為txlogd.conf的位置。 |
| 感測器錯誤3019:vys-log之前未調用vys-cookie。 請與支援部門聯繫。 | 聯繫AdobeClientCare。 |
| 感測器錯誤3025:子請求指回自身 | 聯繫AdobeClientCare。 |

**AOL伺服器**

| 事件消息 | 建議的操作 |
|---|---|
| 感測器錯誤3015:ns/server/[伺服器]/module/[模組] AOLServer配置檔案中缺少節。 | 這是配置錯誤。 正確，如錯誤所述。 |
| 感測器錯誤3019:vys-log之前未調用vys-cookie。 請與支援部門聯繫。 聯繫AdobeClientCare。 | 請與支援部門聯繫。 聯繫AdobeClientCare。 |
| 感測器錯誤3020:VisualSciencesConfig缺少作為第一個條目 [節] 檔案中。 | 這是配置錯誤。 正確，如錯誤所述。 |
| 感測器錯誤3021:VisualSciencesConfig缺少值 [節] 檔案中。 | 這是配置錯誤。 正確，如錯誤所述。 |

**iPlanet和Java System Web伺服器**

| 事件消息 | 建議的操作 |
|---|---|
| 感測器錯誤3011:需要Init指令。 如Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | 這是配置錯誤。 缺少iPlanet init指令。 |
| 感測器錯誤3015:在iPlanet Init指令中未指定config-file | 這是配置錯誤。 在iPlanet Init指令中未提供配置檔案的路徑。 |
| 感測器錯誤3019:vys-log之前未調用vys-cookie。 請檢查配置檔案 | 必須為每個軟體虛擬伺服器指定vys-cookie作為第一個NameTrans指令。 |
