---
description: Data Workbench監控設定檔的安裝指示。
title: 安裝監控設定檔
uuid: e0d6fc61-d9b9-4c4b-94e1-2acfd0ff4de6
exl-id: 368e489c-75c9-4402-a709-a4f5987459b6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1052'
ht-degree: 0%

---

# 安裝監控設定檔{#installing-the-monitoring-profile}

{{eol}}

Data Workbench監控設定檔的安裝指示。

## 安裝步驟 {#section-d4355dbea8a447f48ab168db6ccff612}

1. 將新的Sensor實例配置為將其用於標籤的網頁資料收集。 確保zig.gif檔案位於Sensor Web伺服器文檔根目錄中。 感測器可以在與監視器配置檔案相同的主機上運行。 （如果為此目的使用文字檔案，則不會發生此問題。）

   >[!NOTE]
   >
   >此感測器實例必須專用於僅接收來自監視代理的通信。 此外，如果為此集合重新配置Web伺服器，可將感測器配置為在其他埠上運行。

1. 在 [!DNL txlogd.conf] 檔案中有預設行：

   ```
   <b>ContentFilterExclude</b> image/,text/css,application/x-javascript,text/javascript
   ```

   對於Data Workbench監控設定檔應用程式（或任何「已標籤」的頁面實作），必須移除影像類型，才能透過GIF檔案收集。 更新的行是：

   ```
   <b>ContentFilterExclude </b>text/css,application/x-javascript,text/javascript
   ```

1. 複製 [!DNL insight_monitor.zip/insight_monitor_agent] 到臨時位置。
1. 更新 [!DNL insight_monitor_agent.cfg] 檔案。 請依照設定檔案中的註解操作：

   **監視配置檔案：**

   ![](assets/monitor_agent_cfg_sensor.png)

   定義您要收集所有資訊的位置，並提供URL位址。 這必須是專用感測器，除此應用程式外，不會收到任何流量。

   ![](assets/monitor_agent_cfg_dump.png)

   有些路徑假設有e:磁碟。 您可能想要根據您的環境變更此路徑。

   ![](assets/monitor_agent_cfg_quickcheck.png)

   執行轉換設定檔時，Data Workbench可能會停止回應。 如果程式連續三次無反應，此值可讓您傳送警報。 這是減少誤報警報的方法。

   ![](assets/monitor_agent_cfg_groups.png)

   這是您設定環境和群組維度的位置。 這可能與主機不同。

   這是w ![](assets/monitor_agent_cfg_debug.png)在此，您可以查看此路徑中的錯誤日誌，從而確切地查看監視器代理正在執行的操作。

   ![](assets/monitor_agent_cfg_tempdb.png)

   這是內部使用臨時資料庫。 當達到容量時，可能會收到警報。 這與物理磁碟的使用情況不同。

1. 複製 *insight_monitor_agent* 資料夾，傳送至執行data workbench伺服器的每個DPU和FSU主機。 組態檔中指出的預設位置為 [!DNL e:\insight_monitor_agent] 但你可以改變這個位置。

1. 每10分鐘添加一個Windows計畫任務以調用代理（在處理率計算中假定此期間）。 計畫是 [!DNL e:insight_monitor/insight_monitor_agent.exe]. 引數為config-file e:\insight_monitor\insight_monitor.cfg。 從e:\insight_monitor開始。 運行執行任務的用戶必須具有讀/寫權限 [!DNL e:\insight_monitor] 並讀取Win32 OLE對象 [!DNL root\CIMV2] （需要確定data workbench伺服器服務啟動模式，並檢查本機磁碟上的空間百分比）

1. 確認VSL檔案會隨著監視器記錄累積而開始成長。 這需要一些時間，因為小型安裝中的流量會非常低（每10分鐘，代理程式就只會針對主機特定資料傳送一次點擊，另外每個處理設定檔傳送一次點擊）。
1. 將insight_monitor.zip\profiles\Insight Historic解壓縮到臨時位置。
1. 在中更新主機名 [!DNL profile.cfg], [!DNL dataset\cluster.cfg]，和 [!DNL dataset\segment export.cfg].

1. 將檔案更新至Data Workbench設定檔目錄。
1. 更新日誌伺服器和路徑 [!DNL dataset\log processing.cfg] 到Sensor VSL累積的位置。
1. [（可選）] 對設定檔執行相同操作 [!DNL Insight Profile Status] 和 [!DNL Insight Server Status]. 此外，每晚應重新處理狀態設定檔，並附上兩天回溯視窗。 添加Windows計畫任務：計畫是 [!DNL e:\insight_monitor\insight_reprocess.exe]. 引數為 [!DNL --profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. 離開 [!DNL start in] 空白。 為添加另一個計畫任務 *&quot;insight server狀態&quot;*. *insight_reprocess.exe* 需要讀/寫訪問 *log processing.cfg* 以更新開始時間。

1. 此外，每晚應重新處理狀態設定檔，並附上兩天回溯視窗。 添加Windows計畫任務：計畫是 *e:\insight_monitor\insight_reprocess.exe*. 理由是。 [!DNL -profile-path="PATH TO PROFILES\insight profile status" --start-days-ago=2]. 離開 *開始* 空白。 為添加另一個計畫任務 [!DNL "insight server status"]. [!DNL insight_reprocess.exe] 需要讀/寫訪問 [!DNL log processing.cfg] 以更新開始時間。 確認每個設定檔都在累積時讀取監視器VSL。 同樣地，這需要一些時間 — 可能需要幾個小時 — 因為容量極低。

## 安裝說明 {#section-17722441ab0046fcbcb46b957d56230a}

* **在授權測試環境中設定監控設定檔**. 您的Data Workbench實施隨附測試環境套件，可讓您安裝及設定應用程式。 如果在生產FSU或DPU伺服器上安裝，則您需要將伺服器配置為在單獨的埠上運行。
* **為監視配置檔案專門部署新感測器**. 您需要將新的Sensor實例安裝到運行Monitoring Profile的伺服器。 這是Sensor生產實例的補充。 (在生產伺服器或非生產伺服器上安裝Sensor（專為監控配置檔案）無需額外付費。)
* **在Data Workbench維護期間停用監視器代理**. 為避免污染正常運行時間和效能指標，您可以將服務InsightServer(Omniture Insight伺服器)的服務啟動模式設為手動。 一個實用的PowerShell命令是 *set-service -name insightserver -startuptype手動*. 在維護後將其設回自動： *set-service -name insightserver -startuptype自動*. 另一個選項是暫時禁用監視器代理計畫任務。
* **狀態配置檔案需要一個尾隨窗口** 刪除舊主機和配置檔案以及舊主機配置檔案映射。 不過，如果事件資料量如此小，以至於Data Workbench不會緩衝資料，則您可能需要稍微擴充視窗的大小，才能加以處理。
* **代理程式會從Data Workbench收集整體和最舊的截止時間詳細狀態**，此量度會以本機主機時間報告，假設事件資料記錄時間戳記為UTC(如VSL檔案)。 如果事件資料時間戳記位於非UTC時區，則截止時間會在產生的「分析設定檔狀態」設定檔中偏移。 若 **all** 事件資料時間戳記所在的時區相同，您可以將該位移新增至 *分析設定檔狀態\度量\截止延遲分鐘數。metric*.

* **推出兩個新維度，以協助客戶將其伺服器分組（若伺服器處於不同狀態）**，例如生產、測試、測試伺服器和其他狀態的伺服器。 例如，如果您要查找「正常運行時間」，則只查看生產模式下的伺服器。 因此，群組維度只是另一種根據您的需求任意分組伺服器的方式。 例如，在「監視配置」檔案中，您可以設定哪個主機托管您的部門正在提供服務，如操作、開發或市場營銷。
