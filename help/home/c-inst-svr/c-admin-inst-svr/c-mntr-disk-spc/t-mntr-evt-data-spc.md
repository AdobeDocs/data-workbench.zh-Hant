---
description: 有關監視事件資料空間和更改感測器資料日誌目錄的資訊。
solution: Analytics
title: 監控事件資料空間
uuid: e514e8fb-e735-4003-ab21-17470c73af37
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---


# 監控事件資料空間{#monitoring-event-data-space}

有關監視事件資料空間和更改感測器資料日誌目錄的資訊。

**建議頻率：** 每5-10分鐘

[!DNL Insight Server] 根據您的配置，每天 [!DNL Sensor] 在資料處理單元或檔案伺服器單元上儲存一個日誌檔案。 記錄檔的大小和所需的資料儲存空間量取決於許多變數，例如，記錄的網站數量以及您的Web伺服器每秒收到的請求數。

一般安裝 [!DNL Insight Server] (或叢集 [!DNL Insight Server] )可儲存數TB的資料，假設實作使用Adobe建議的硬體來存 [!DNL Insight Server] 放機器。

通常，所有日誌資料都保留在計算 [!DNL Insight Server] 機上。 如果有必要在機器上增加可用的資料儲存空間，您可以將除最新記錄檔以外的所有資料儲存空間移至其他機器或資料儲存媒體（zip drive、磁帶等）。 移動資料並不需要您停止 [!DNL Insight Server]，也不會影響任何可能連線並使用連續資料 [!DNL Insights] 的功能 [!DNL Insight Server] 。 如果您不處理或重新處理分析資料集，則保留對所有先前資料的存取權，而新資料將繼續在中提供 [!DNL Insight]。 如果您處理或重新處理分析資料集，則必須先處理完成，才能存取資料。

預設情況下，由生成並傳 [!DNL Sensor] 輸到的事件數 [!DNL Insight Server] 據儲存在安裝 [!DNL Logs] 目錄內的 [!DNL Insight Server] 資料夾中。 通信配置檔案， [!DNL Communications.cfg]指定由讀取的事件資料日誌檔案的位置 [!DNL Insight Server]。

**更改資料的日誌目[!DNL Sensor]錄**

1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。
1. 按一下右鍵要配置的 [!DNL Insight Server] 表徵圖，然後按一下 **[!UICONTROL Server Files]**。
1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Components]** 查看其內容。 文 [!DNL Communications.cfg] 件位於此目錄中。
1. 按一下右鍵的伺服器名 *稱列中的複選標籤* ，然 [!DNL Communications.cfg] 後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在的 [!DNL Temp] 列中 [!DNL Communications.cfg]。
1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。
1. 在視窗 [!DNL Communications.cfg] 中，按一 **[!UICONTROL component]** 下以檢視其內容。
1. 在視窗 [!DNL Communications.cfg] 中，按一 **[!UICONTROL Servers]** 下以檢視其內容。 可能會出現幾種類型的伺服器：檔案伺服器、日誌伺服器、初始化伺服器、狀態伺服器、發送伺服器或複製伺服器。
1. 查找LoggingServer(即LoggingServer中要由其 [!DNL Sensor] 處理的日誌檔案), [!DNL Insight Server]然後按一下其編號以查看菜單。

   ![步驟資訊](assets/cfg_communications_examplevalues_logging.png)

   預設日誌目錄是安 [!DNL Logs] 裝目錄內 [!DNL Insight Server] 的資料夾。

1. 編輯日誌目錄參數以反映所需的日誌檔案位置。

   >[!NOTE]
   >
   >請勿修改LoggingServer的任何其他參數。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   「伺服器」節點下可能會列出多個檔案伺服器，因此您可能需要查看其中許多檔案伺服器的內容（通過按一下清單中的數字），以查找具有要修改的本地日誌路徑的伺服器。 [!DNL Servers]

1. 編輯本機路徑以反映所需檔案的位 [!DNL .vsl] 置。

   >[!NOTE]
   >
   >不要修改FileServer的任何其他參數。

   儘管日誌檔案的位置已在檔案中更改，但 [!DNL Communications.cfg] 您可以通過指定/Logs/作為FileServer的URI將這些檔案映射到 [!DNL Server Files Manager] 的Logs目錄。

1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Server Files Manager]按一下右鍵列中檔案的複選標籤，然 [!DNL Temp] 後選擇 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

