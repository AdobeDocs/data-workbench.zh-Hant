---
description: 有關監視事件資料空間和更改感測器資料日誌目錄的資訊。
title: 監控事件資料空間
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# 監控事件資料空間{#monitoring-event-data-space}

{{eol}}

有關監視事件資料空間和更改感測器資料日誌目錄的資訊。

**建議頻率：** 每5-10分鐘

[!DNL Insight Server] 每個儲存一個日誌檔案 [!DNL Sensor] 資料處理單元或檔案伺服器單元，視您的設定而定。 記錄檔的大小和所需的資料儲存空間量取決於許多變數，例如記錄的網站數量和您的Web伺服器每秒收到的請求數。

典型的 [!DNL Insight Server] (或 [!DNL Insight Server] 群集)能夠儲存多TB的資料，假設實施使用Adobe建議的硬體 [!DNL Insight Server] 機器。

通常，所有記錄資料都會保留在 [!DNL Insight Server] 機器。 如果有必要在電腦上提供更多資料儲存空間，您可以將除當前日誌檔案之外的所有日誌檔案移動到其他電腦或資料儲存介質（zip驅動器、磁帶等）。 移動資料不需要停止 [!DNL Insight Server]，而不會影響任何 [!DNL Insights] 可能與 [!DNL Insight Server] 和處理連續資料。 如果您不處理或重新處理分析資料集，便可保留所有先前資料的存取權，而新資料仍可繼續在 [!DNL Insight]. 如果您處理或重新處理分析資料集，在處理完成前無法存取資料。

依預設，由產生的事件資料 [!DNL Sensor] 並傳送至 [!DNL Insight Server] 儲存於 [!DNL Logs] 資料夾 [!DNL Insight Server] 安裝目錄。 通信配置檔案， [!DNL Communications.cfg]，指定讀取的事件資料日誌檔案的位置 [!DNL Insight Server].

**更改的日誌目錄 [!DNL Sensor] 資料**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下 [!DNL Insight Server] 要配置，請按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Communications.cfg] 檔案位於此目錄中。
1. 以滑鼠右鍵按一下 *伺服器名稱* 欄 [!DNL Communications.cfg] 按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Communications.cfg].
1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. 在 [!DNL Communications.cfg] 按一下 **[!UICONTROL component]** 來檢視其內容。
1. 在 [!DNL Communications.cfg] 按一下 **[!UICONTROL Servers]** 來檢視其內容。 可能會出現數種伺服器：檔案伺服器、日誌伺服器、初始化伺服器、狀態伺服器、發送伺服器或複製伺服器。
1. 查找LoggingServer，該位置 [!DNL Sensor] 將其日誌檔案寫入，由 [!DNL Insight Server]，然後按一下其編號以檢視功能表。

   ![步驟資訊](assets/cfg_communications_examplevalues_logging.png)

   預設日誌目錄為 [!DNL Logs] 資料夾 [!DNL Insight Server] 安裝目錄。

1. 編輯日誌目錄參數以反映日誌檔案的所需位置。

   >[!NOTE]
   >
   >請勿修改LoggingServer的任何其他參數。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   多個FileServer可能列在「伺服器」節點下，因此您可能需要查看其中許多FileServer的內容(方法是按一下 [!DNL Servers] 清單)，查找要修改的「本地路徑」為的伺服器。

1. 編輯本機路徑以反映 [!DNL .vsl] 檔案。

   >[!NOTE]
   >
   >請勿修改FileServer的任何其他參數。

   雖然記錄檔的位置已在 [!DNL Communications.cfg] 檔案，可將這些檔案對應至 [!DNL Server Files Manager] 將/Logs/指定為FileServer的URI。

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄和選取 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
