---
description: 您應定期監控事件記錄檔，以追蹤記錄至的Insight Server系統事件訊息 <yyyymmdd>-event.txt檔案，預設位於Insight Server安裝目錄內的「事件」資料夾中。
title: 監控管理事件(Insight Server)
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 1%

---

# 監控管理事件{#monitoring-administrative-events}

{{eol}}

您應定期監控事件記錄檔，以追蹤記錄至的Insight Server系統事件訊息 `<YYYYMMDD>-event.txt` 檔案，預設位於Insight Server安裝目錄的「事件」資料夾中。

**建議頻率：** 每5-10分鐘

您可以使用 [!DNL Server Files Manager] in [!DNL Insight]，您的自動化管理工具， [!DNL *-event.txt] 檔案或Windows事件查看器。

>[!NOTE]
>
>管理事件日誌與Windows事件日誌完全不同，但包含一些相同的事件。 管理事件日誌僅包含有關 [!DNL Insight Server] 事件。

**若要檢視events.txt檔案，請透過[!DNL Server Files Manager]**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下作用中的圖示 [!DNL Insight Server] 按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Events]** 來檢視其內容。
1. 以滑鼠右鍵按一下 *伺服器名稱* 欄，然後按一下 **[!UICONTROL Make Local]**. 中的檔案名稱旁會出現勾選記號 [!DNL Temp] 欄。
1. 以滑鼠右鍵按一下 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 事件檔案會顯示在新的Microsoft Windows Notepad窗口中。

   ![步驟資訊](assets/vis_FileManager_eventfile.png)

   此 [!DNL Server.log] 檔案 [!DNL Trace] 資料夾 [!DNL Insight Server] 安裝目錄包含更詳細的記錄資訊。

**通過Windows事件查看器查看事件**

* 按一下 **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**更改管理事件日誌目錄**

管理事件日誌配置檔案， [!DNL Administrative Events Log.cfg]，指定輸出事件記錄的目錄。

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。

1. 以滑鼠右鍵按一下 [!DNL Insight Server] 要配置，請按一下 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Administrative Event Logs.cfg] 檔案位於此目錄中。

1. 以滑鼠右鍵按一下 *伺服器名稱* 欄 [!DNL Administrative Event Logs.cfg] 按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Administrative Event Logs.cfg].

1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. 在 [!DNL Administrative Event Logs.cfg] 按一下 **[!UICONTROL component]** 來檢視其內容。 預設路徑為 [!DNL Events] 資料夾 [!DNL Insight Server] 安裝目錄。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在Path參數中，鍵入要輸出事件日誌記錄資料的目錄的名稱。
1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.
   1. 在 [!DNL Server Files Manager]，請在 [!DNL Temp] 欄和選取 **[!UICONTROL Save to]** > **[!UICONTROL server name]**.
