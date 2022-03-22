---
description: 您應定期監視事件日誌檔案以跟蹤Insight Server系統事件消息，這些消息記錄到 <yyyymmdd>-event.txt檔案，預設位於Insight Server安裝目錄的「事件」資料夾中。
title: 監視管理事件(Insight Server)
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# 監控管理事件{#monitoring-administrative-events}

您應定期監視事件日誌檔案以跟蹤Insight Server系統事件消息，這些消息記錄到 `<YYYYMMDD>-event.txt` 預設情況下位於Insight Server安裝目錄中的Events資料夾中的檔案。

**推薦頻率：** 每五至十分鐘

可以使用 [!DNL Server Files Manager] 在 [!DNL Insight]，您的自動管理工具， [!DNL *-event.txt] 檔案或Windows事件查看器。

>[!NOTE]
>
>管理事件日誌與Windows事件日誌完全分開，但包含一些相同的事件。 管理事件日誌僅包含有關 [!DNL Insight Server] 事件。

**通過查看events.txt檔案[!DNL Server Files Manager]**

1. 在 [!DNL Insight]的 [!DNL Admin] > [!DNL Dataset and Profile] 頁籤 **[!UICONTROL Servers Manager]** 縮略圖以開啟「伺服器管理器」(Servers Manager)工作區。
1. 按一下右鍵活動的表徵圖 [!DNL Insight Server] 按一下 **[!UICONTROL Server Files]**。
1. 在 [!DNL Server Files Manager]按一下 **[!UICONTROL Events]** 來查看其內容。
1. 按一下右鍵 *伺服器名稱* 列，然後按一下 **[!UICONTROL Make Local]**。 在中的檔案名旁邊顯示複選標籤 [!DNL Temp] 的雙曲餘切值。
1. 按一下右鍵 [!DNL Temp] 列，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 事件檔案將出現在新的MicrosoftWindows記事本窗口中。

   ![步驟資訊](assets/vis_FileManager_eventfile.png)

   的 [!DNL Server.log] 檔案 [!DNL Trace] 資料夾 [!DNL Insight Server] 安裝目錄包含更詳細的日誌記錄資訊。

**通過Windows事件查看器查看事件**

* 按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**。

**更改管理事件日誌目錄**

管理事件日誌配置檔案， [!DNL Administrative Events Log.cfg]，指定事件記錄輸出到的目錄。

1. 在 [!DNL Insight]的 [!DNL Admin] > [!DNL Dataset and Profile] 頁籤 **[!UICONTROL Servers Manager]** 縮略圖以開啟「伺服器管理器」(Servers Manager)工作區。

1. 按一下右鍵 [!DNL Insight Server] 要配置並按一下 **[!UICONTROL Server Files]**。

1. 在 [!DNL Server Files Manager]按一下 **[!UICONTROL Components]** 來查看其內容。 的 [!DNL Administrative Event Logs.cfg] 檔案位於此目錄中。

1. 按一下右鍵 *伺服器名稱* 列 [!DNL Administrative Event Logs.cfg] 按一下 **[!UICONTROL Make Local]**。 在 [!DNL Temp] 列 [!DNL Administrative Event Logs.cfg]。

1. 按一下右鍵中新建立的複選標籤 [!DNL Temp] 列，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 在 [!DNL Administrative Event Logs.cfg] 窗口，按一下 **[!UICONTROL component]** 來查看其內容。 預設路徑為 [!DNL Events] 資料夾 [!DNL Insight Server] 安裝目錄。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在「路徑」參數中，鍵入要向其輸出事件日誌資料的目錄的名稱。
1. 通過執行以下操作將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 按一下 **[!UICONTROL Save]**。
   1. 在 [!DNL Server Files Manager]，按一下右鍵 [!DNL Temp] 列和選擇 **[!UICONTROL Save to]** > **[!UICONTROL server name]**。
