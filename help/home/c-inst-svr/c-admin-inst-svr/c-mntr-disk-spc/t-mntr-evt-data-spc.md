---
description: 有關監視事件資料空間和更改感測器資料日誌目錄的資訊。
title: 監控事件資料空間
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# 監控事件資料空間{#monitoring-event-data-space}

有關監視事件資料空間和更改感測器資料日誌目錄的資訊。

**建議頻率：** 每5-10分鐘

[!DNL Insight Server] 根據您的配置， [!DNL Sensor] 每天在資料處理單元或檔案伺服器單元上儲存一個日誌檔案。記錄檔的大小和所需的資料儲存空間量取決於許多變數，例如記錄的網站數量和您的Web伺服器每秒收到的請求數。

假設實施使用Adobe為[!DNL Insight Server]電腦建議的硬體，典型的[!DNL Insight Server]（或[!DNL Insight Server]群集）安裝能夠儲存多TB的資料。

通常，所有日誌資料都保留在[!DNL Insight Server]電腦上。 如果有必要在電腦上提供更多資料儲存空間，您可以將除當前日誌檔案之外的所有日誌檔案移動到其他電腦或資料儲存介質（zip驅動器、磁帶等）。 移動資料不要求您停止[!DNL Insight Server]，而且它不會影響任何可連接到[!DNL Insight Server]並使用連續資料的[!DNL Insights]中可用的功能。 如果您不處理或重新處理分析資料集，便可保留對所有先前資料的存取權，而新資料仍可在[!DNL Insight]中使用。 如果您處理或重新處理分析資料集，在處理完成前無法存取資料。

預設情況下，由[!DNL Sensor]產生並傳輸到[!DNL Insight Server]的事件資料儲存在[!DNL Insight Server]安裝目錄的[!DNL Logs]資料夾中。 通信配置檔案[!DNL Communications.cfg]指定由[!DNL Insight Server]讀取的事件資料日誌檔案的位置。

**更改資料的日誌目 [!DNL Sensor] 錄**

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Communications.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Communications.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Communications.cfg]的[!DNL Temp]列中出現複選標籤。
1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Communications.cfg]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。
1. 在[!DNL Communications.cfg]窗口中，按一下&#x200B;**[!UICONTROL Servers]**&#x200B;查看其內容。 可能會出現數種伺服器：檔案伺服器、日誌伺服器、初始化伺服器、狀態伺服器、發送伺服器或複製伺服器。
1. 查找LoggingServer，此處[!DNL Sensor]將寫入其要由[!DNL Insight Server]處理的日誌檔案，然後按一下其編號以查看菜單。

   ![步驟資訊](assets/cfg_communications_examplevalues_logging.png)

   預設日誌目錄是[!DNL Insight Server]安裝目錄內的[!DNL Logs]資料夾。

1. 編輯日誌目錄參數以反映日誌檔案的所需位置。

   >[!NOTE]
   >
   >請勿修改LoggingServer的任何其他參數。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   多個FileServer可能列在「伺服器」節點下，因此您可能需要查看其中許多的內容（通過按一下[!DNL Servers]清單中的編號），以查找具有要修改的日誌的本地路徑的伺服器。

1. 編輯本地路徑以反映[!DNL .vsl]檔案的所需位置。

   >[!NOTE]
   >
   >請勿修改FileServer的任何其他參數。

   儘管日誌檔案在[!DNL Communications.cfg]檔案中的位置已更改，但可以通過指定/Logs/作為FileServer的URI將這些檔案映射到[!DNL Server Files Manager]的Logs目錄。

1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。
