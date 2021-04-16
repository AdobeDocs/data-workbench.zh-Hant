---
description: 要盡快檢測感測器錯誤並在導致重大問題或中斷之前進行修復，您應定期監控事件日誌。
title: 監控管理事件
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# 監控管理事件{#monitoring-administrative-events}

要盡快檢測感測器錯誤並在導致重大問題或中斷之前進行修復，您應定期監控事件日誌。

**建議頻率：** 至少每小時

您可以使用Windows事件查看器或Unix Syslog檔案以及[!DNL Sensor]安裝目錄中[!DNL Logs]資料夾中預設的[!DNL *.sensor-log]檔案來監視這些事件。 這些檔案表示在資料收集過程中存在錯誤，特別是當[!DNL Sensor]無法連接到目標[!DNL data workbench server]並啟動排隊資料時。

## 在Windows {#section-7c0443a356af4381bf22259654f5cd17}上監視事件

感測器將錯誤記錄到源為「Adobe」的Windows事件查看器的應用程式日誌中。

消息會記錄為「資訊」、「警告」或「錯誤」，具體取決於其嚴重性。

**要開啟Windows事件查看器**:

* 按一下「**開始>控制面板>管理工具>事件檢視器**」。

## 在Unix上監視事件{#section-5de3947891fb47ac88b7c855e545d54a}

感測器將錯誤記錄到[!DNL syslog]守護程式。

syslog守護程式根據您在syslog.conf檔案中指定的規則將錯誤消息寫入日誌檔案。 根據嚴重性，錯誤會以標籤&quot;LOG_DAEMON&quot;和&quot;LOG_NOTICE&quot;或&quot;LOG_ERR&quot;記錄。

**開啟Unix系統日誌**

Unix系統日誌通常位於[!DNL /var/adm/messages]或[!DNL /var/log/messages]中。

瀏覽至適當位置並開啟syslog。

## 瞭解消息格式{#section-a0899add30fd4b2da58a23b9e3324693}

所有感測器消息都包含&quot;Sensor&quot;字串，並編號以反映所顯示消息的重要性。

| 訊息編號 | 訊息含義 | 消息字串 |
|---|---|---|
| 1xxx | 資訊性 | 感測器資訊# |
| 2xxx | 警告 | 感測器警告# |
| 3xxx | 配置錯誤 | 感測器錯誤號 |
| 4xxx | 操作錯誤 | 感測器錯誤號 |
| 5xxx | 內部錯誤 | 感測器錯誤號 |

>[!NOTE]
>
>警告(2xxx)目前未使用。 這些數字將保留供將來使用。

您的網路管理工具可設定為每5-10分鐘監視一次消息，以發現「感測器」源出錯，並提醒相關人員可能需要干預的問題。 您可以選擇只監視某些類型的事件消息（如「感測器錯誤」字串）的系統。 或者，您可以對前面有「感測器資訊」、「感測器警告」和「感測器錯誤」字串的事件應用不同的規則。

## 識別重要消息{#section-5a20f5dc18ca4012931d194db855e54e}

在事件日誌中，您應特別注意並立即處理與隊列大小相關的任何消息。

例如，&quot;[!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot;等訊息需要注意。

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
   <td colname="col2"> 不需執行任何動作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1011:感測器已終止。 佇列的點按總數## </td> 
   <td colname="col2"> 不需執行任何動作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1012:Adobe磁碟隊列已滿#% </td> 
   <td colname="col2"> 每次磁碟隊列利用率超過10%閾值時都記錄此消息。 如果此百分比繼續增加，則應在隊列已滿且資料丟失之前採取措施。 最有可能的問題是感測器已停止與Insight Server通信。 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1013:感測器配置已更改 </td> 
   <td colname="col2"> 不需執行任何動作。 感測器在其配置檔案中檢測到更改並將重新載入。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1014:問題種子隨機數產生器 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1016:已載入配置檔案檔案名 </td> 
   <td colname="col2"> 不需執行任何動作。 感測器已成功載入列出的配置檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器資訊1017:載入實驗檔案檔案名 </td> 
   <td colname="col2"> 不需執行任何動作。 感測器成功載入了列出的實驗檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3016:無法載入配置檔案/mypath/myfile </td> 
   <td colname="col2"> 確認在Web伺服器配置中指定的感測器配置檔案存在並具有Web伺服器進程所需的讀取權限。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>感測器3017:無法載入受控實驗配置檔案/mypath/myfile </p> </td> 
   <td colname="col2"> <p>確認txlogd.conf中指定的受控實驗檔案存在，並且txlogd進程具有讀取檔案所需的權限。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3018:無法解析內容篩選器清單。 檢查txlogd配置檔案 </td> 
   <td colname="col2"> 驗證txlogd.conf中ContentFilterInclude和ContentFilterExclude項的語法。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3023:無法建立鎖(g_lockThrottle) </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤3024:無法建立鎖定(g_lockConfigCheck) </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
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
   <td colname="col1"> 感測器錯誤4021:佇列已滿 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤4022:無法映射長度&lt;x&gt;在偏移&lt;y&gt;處的記憶體塊 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5012:無法建立互斥鎖。 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5013:無法獲取互斥鎖。 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5030:衍生分叉錯誤。 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5031:setsid失敗。 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5032:衍生分叉錯誤。 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5033:chdir失敗。 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5034:接收的信號 </td> 
   <td colname="col2"> 程式可能由外部信號終止。 如果無法判斷此訊號的來源，請連絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5035:從外部主目錄呼叫的退出 </td> 
   <td colname="col2"> 聯絡AdobeClientCare。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器錯誤5036:txlogd已在運行 </td> 
   <td colname="col2"> txlogd守護程式的另一個實例已在運行。 如果要運行新實例，請先停止另一個實例。 </td> 
  </tr> 
 </tbody> 
</table>

**Apache/IBM HTTP Server**

| 事件訊息 | 建議的動作 |
|---|---|
| 感測器錯誤3015:httpd.conf中缺少VisualSciencesConfig指令。 | 這是配置錯誤。 VisualSciencesConfig指令必須位於httpd.conf中，且參數為txlogd.conf的位置。 |
| 感測器錯誤3019:vys-cookie未在vys-log之前呼叫。 請聯絡支援。 | 聯絡AdobeClientCare。 |
| 感測器錯誤3025:子請求點返回本身 | 聯絡AdobeClientCare。 |

**AOL Server**

| 事件訊息 | 建議的動作 |
|---|---|
| 感測器錯誤3015:ns/server/[server]/module/[module]部分在AOLServer配置檔案中缺失。 | 這是配置錯誤。 正確無誤。 |
| 感測器錯誤3019:vys-cookie未在vys-log之前呼叫。 請聯絡支援。 聯絡AdobeClientCare。 | 請聯絡支援。 聯絡AdobeClientCare。 |
| 感測器錯誤3020:VisualSciencesConfig在AOLServer配置檔案的[section]部分中缺少作為第一個條目。 | 這是配置錯誤。 正確無誤。 |
| 感測器錯誤3021:VisualSciencesConfig在AOLServer配置檔案的[section]部分中缺少值。 | 這是配置錯誤。 正確無誤。 |

**iPlanet和Java System Web伺服器**

| 事件訊息 | 建議的動作 |
|---|---|
| 感測器錯誤3011:需要初始化指令。 例如，Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | 這是配置錯誤。 缺少iPlanet init指令。 |
| 感測器錯誤3015:iPlanet Init指令中未指定config-file | 這是配置錯誤。 iPlanet Init指令中未提供配置檔案的路徑。 |
| 感測器錯誤3019:vys-cookie未在vys-log之前呼叫。 請檢查配置檔案 | vys-cookie必須指定為每個軟體虛擬伺服器的第一個NameTrans指令。 |
