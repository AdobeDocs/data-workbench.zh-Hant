---
description: 有關監視事件資料空間和更改感測器資料日誌目錄的資訊。
title: 監控事件資料空間
uuid: e514e8fb-e735-4003-ab21-17470c73af37
exl-id: 1016d00f-e0a0-47f1-a600-528c4811fcf6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 1%

---

# 監控事件資料空間{#monitoring-event-data-space}

有關監視事件資料空間和更改感測器資料日誌目錄的資訊。

**建議頻率：** 每5-10分鐘

[!DNL Insight Server] 根據您的配置，每天 [!DNL Sensor] 在資料處理單元或檔案伺服器單元上儲存一個日誌檔案。記錄檔的大小和所需的資料儲存空間量取決於許多變數，例如，記錄的網站數量以及您的Web伺服器每秒收到的請求數。

典型的[!DNL Insight Server]（或[!DNL Insight Server]群集）安裝能夠儲存多TB的資料，前提是實施使用[!DNL Insight Server]電腦的Adobe建議的硬體。

通常，所有日誌資料在[!DNL Insight Server]電腦上仍然存在。 如果有必要在機器上增加可用的資料儲存空間，您可以將除最新記錄檔以外的所有資料儲存空間移至其他機器或資料儲存媒體（zip drive、磁帶等）。 移動資料不要求您停止[!DNL Insight Server]，並且它不會影響任何可連接到[!DNL Insight Server]並使用連續資料的[!DNL Insights]中可用的功能。 如果您不處理或重新處理分析資料集，則保留對所有先前資料的存取權，而新資料仍可繼續在[!DNL Insight]中使用。 如果您處理或重新處理分析資料集，則必須先處理完成，才能存取資料。

預設情況下，由[!DNL Sensor]生成並傳輸到[!DNL Insight Server]的事件資料儲存在[!DNL Insight Server]安裝目錄的[!DNL Logs]資料夾中。 通信配置檔案[!DNL Communications.cfg]指定由[!DNL Insight Server]讀取的事件資料日誌檔案的位置。

**更改資料的日誌目 [!DNL Sensor] 錄**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Communications.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Communications.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Communications.cfg]的[!DNL Temp]欄中會出現複選標籤。
1. 在[!DNL Temp]欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。
1. 在[!DNL Communications.cfg]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。
1. 在[!DNL Communications.cfg]窗口中，按一下&#x200B;**[!UICONTROL Servers]**&#x200B;查看其內容。 可能會出現幾種類型的伺服器：檔案伺服器、日誌伺服器、初始化伺服器、狀態伺服器、發送伺服器或複製伺服器。
1. 查找[!DNL Sensor]寫入[!DNL Insight Server]要處理的日誌檔案的LoggingServer ，然後按一下其編號以查看菜單。

   ![步驟資訊](assets/cfg_communications_examplevalues_logging.png)

   預設日誌目錄是[!DNL Insight Server]安裝目錄內的[!DNL Logs]資料夾。

1. 編輯日誌目錄參數以反映所需的日誌檔案位置。

   >[!NOTE]
   >
   >請勿修改LoggingServer的任何其他參數。

   ![](assets/cfg_communicates_logslocalpath_egvalues.png)

   多個檔案伺服器可能列在「伺服器」節點下，因此您可能需要查看其中許多伺服器的內容（通過按一下[!DNL Servers]清單中的數字），以查找具有要修改的本地日誌路徑的伺服器。

1. 編輯本機路徑以反映[!DNL .vsl]檔案的所需位置。

   >[!NOTE]
   >
   >不要修改FileServer的任何其他參數。

   雖然日誌檔案的位置在[!DNL Communications.cfg]檔案中已經更改，但可以通過指定/Logs/作為FileServer的URI將這些檔案映射到[!DNL Server Files Manager]的Logs目錄。

1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。
