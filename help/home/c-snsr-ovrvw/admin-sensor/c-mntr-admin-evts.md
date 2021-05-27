---
description: 要盡快檢測感測器錯誤，並在引起嚴重問題或中斷之前修復這些錯誤，您應定期監視事件日誌。
title: 監控管理事件
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# 監控管理事件{#monitoring-administrative-events}

要盡快檢測感測器錯誤，並在引起嚴重問題或中斷之前修復這些錯誤，您應定期監視事件日誌。

**建議頻率：** 至少每小時

可以使用預設位於[!DNL Sensor]安裝目錄內[!DNL Logs]資料夾中的Windows事件查看器或Unix Syslog檔案和[!DNL *.sensor-log]檔案來監視這些事件。 這些檔案指示在資料收集期間是否存在錯誤，特別是當[!DNL Sensor]無法連接到目標[!DNL data workbench server]並開始排隊資料時。

## 在Windows {#section-7c0443a356af4381bf22259654f5cd17}上監視事件

感測器將錯誤記錄到「Adobe」源的Windows事件查看器的應用程式日誌中。

訊息會記錄為「資訊」、「警告」或「錯誤」（視其嚴重程度而定）。

**要開啟Windows事件查看器**:

* 按一下「**開始>控制面板>管理工具>事件檢視器**」。

## 在Unix上監視事件{#section-5de3947891fb47ac88b7c855e545d54a}

感測器將錯誤記錄到[!DNL syslog]守護程式。

syslog守護程式根據您在syslog.conf檔案中指定的規則將錯誤消息寫入日誌檔案。 根據嚴重性，以「LOG_DAEMON」和「LOG_NOTICE」或「LOG_ERR」的標誌記錄錯誤。

**開啟Unix系統日誌**

Unix系統日誌通常位於[!DNL /var/adm/messages]或[!DNL /var/log/messages]中。

瀏覽到適當的位置並開啟syslog。

## 了解消息格式{#section-a0899add30fd4b2da58a23b9e3324693}

所有Sensor消息都包含字串&quot;Sensor&quot;，並編號以反映所顯示消息的重要性。

| 消息編號 | 訊息含義 | 訊息字串 |
|---|---|---|
| 1xxx | 資訊 | 感測器資訊# |
| 2xxx | 警告 | 感測器警告# |
| 3xxx | 配置錯誤 | 感測器錯誤# |
| 4xxx | 操作錯誤 | 感測器錯誤# |
| 5xxx | 內部錯誤 | 感測器錯誤# |

>[!NOTE]
>
>警告(2xxx)當前未使用。 這些數字會保留以供日後使用。

您的網路管理工具可以設定為每5-10分鐘監視一次報文，以發現「感測器」源出現錯誤，並提醒適當人員可能需要干預的問題。 您可以選擇僅監視某些類型的事件消息（如「感測器錯誤」字串）的系統。 或者，您可以對帶有「感測器資訊」、「感測器警告」和「感測器錯誤」字串的事件應用不同的規則。

## 識別重要消息{#section-5a20f5dc18ca4012931d194db855e54e}

在事件記錄中，您應特別注意並立即處理任何與佇列大小相關的訊息。

例如，「[!DNL Sensor Info 1012: Adobe disk queue is #% full]」等訊息需要注意。

## 響應感測器事件消息{#section-0004c4a169dc4a8882d9bd87dd326ad4}

描述受支援Web伺服器平台的感測器事件和建議操作的表。

**所有平台**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 事件訊息 </th> 
   <th colname="col2" class="entry"> 建議的動作 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 感測器資訊1010:感測器已初始化。 </td> 
   <td colname="col2"> 無需任何動作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1011:感測器已終止。 排入佇列的點按總次數## </td> 
   <td colname="col2"> 無需任何動作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1012:Adobe磁碟隊列已滿#% </td> 
   <td colname="col2"> 每次磁碟隊列利用率超過10%閾值時都會記錄此消息。 如果此百分比繼續增加，應在佇列已滿且資料遺失之前採取動作。 最有可能的問題是感測器已停止與Insight Server通訊。 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1013:感測器配置已更改 </td> 
   <td colname="col2"> 無需任何動作。 感測器檢測到其配置檔案中的更改，並將重新載入。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1014:問題種子隨機數生成器 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1016:已載入配置檔案檔案名 </td> 
   <td colname="col2"> 無需任何動作。 感測器已成功載入列出的配置檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1017:已載入實驗檔案檔案名 </td> 
   <td colname="col2"> 無需任何動作。 感測器已成功載入列出的實驗檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3016:無法載入配置檔案/mypath/myfile </td> 
   <td colname="col2"> 確認在Web伺服器配置中指定的感測器配置檔案存在，並且具有Web伺服器進程讀取所需的權限。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>感測器3017:無法載入受控實驗配置檔案/mypath/myfile </p> </td> 
   <td colname="col2"> <p>確認txlogd.conf中指定的受控實驗檔案存在，且txlogd程式具有讀取檔案的必要權限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3018:無法解析內容篩選器清單。 檢查txlogd組態檔 </td> 
   <td colname="col2"> 驗證txlogd.conf中ContentFilterInclude和ContentFilterExclude項的語法。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3023:無法建立鎖(g_lockThrottle) </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3024:無法建立鎖(g_lockConfigCheck) </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4014:無法開啟磁碟隊列。 </td> 
   <td colname="col2"> 驗證txlogd.conf中的QueueFile檔案名稱，如果據信正確，請聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4020:不是隊列檔案 </td> 
   <td colname="col2"> 驗證txlogd.conf中的QueueFile檔案名稱，如果據信正確，請聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4021:隊列已滿 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4022:無法映射位移&lt;y&gt;處長度&lt;x&gt;的記憶體塊 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5012:無法建立互斥。 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5013:無法獲取互斥。 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5030:分叉錯誤。 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5031:setsid失敗。 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5032:分叉錯誤。 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5033:chdir失敗。 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5034:已接收信號 </td> 
   <td colname="col2"> 程式可能被外部信號終止。 如果無法確定此信號的來源，請聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5035:從主要外部調用的退出 </td> 
   <td colname="col2"> 請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5036:txlogd已在執行 </td> 
   <td colname="col2"> txlogd守護程式的另一個實例已在運行。 如果要運行新實例，請先停止另一個實例。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server**

| 事件訊息 | 建議的動作 |
|---|---|
| 感測器錯誤3015:httpd.conf中缺少VisualSciencesConfig指令。 | 這是配置錯誤。 VisualSciencesConfig指令必須位於httpd.conf中，且參數為txlogd.conf的位置。 |
| 感測器錯誤3019:vys-log之前未呼叫vys-cookie。 請聯絡支援。 | 請連絡AdobeClientCare。 |
| 感測器錯誤3025:子請求指向本身 | 請連絡AdobeClientCare。 |

**AOL伺服器**

| 事件訊息 | 建議的動作 |
|---|---|
| 感測器錯誤3015:ns/server/[server]/module/[module]部分在AOLServer配置檔案中缺失。 | 這是配置錯誤。 正確無誤。 |
| 感測器錯誤3019:vys-log之前未呼叫vys-cookie。 請聯絡支援。 請連絡AdobeClientCare。 | 請聯絡支援。 請連絡AdobeClientCare。 |
| 感測器錯誤3020:VisualSciencesConfig缺少為AOLServer配置檔案的[section]部分中的第一個條目。 | 這是配置錯誤。 正確無誤。 |
| 感測器錯誤3021:VisualSciencesConfig缺少AOLServer配置檔案的[section]部分中的值。 | 這是配置錯誤。 正確無誤。 |

**iPlanet和Java System Web伺服器**

| 事件訊息 | 建議的動作 |
|---|---|
| 感測器錯誤3011:需要初始化指令。 例如Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | 這是配置錯誤。 缺少iPlanet init指令。 |
| 感測器錯誤3015:在iPlanet Init指令中未指定config-file | 這是配置錯誤。 配置檔案的路徑未在iPlanet Init指令中提供。 |
| 感測器錯誤3019:vys-log之前未呼叫vys-cookie。 請檢查配置檔案 | 必須將vys-cookie指定為每個軟體虛擬伺服器的第一個NameTrans指令。 |
