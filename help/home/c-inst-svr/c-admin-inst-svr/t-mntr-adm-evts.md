---
description: 您應定期監控事件記錄檔以追蹤Insight Server系統事件訊息，這些訊息會記錄至<YYYYMMDD>-event.txt檔案，預設位於Insight Server安裝目錄內的「事件」資料夾。
title: 監控管理事件
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
exl-id: e468a7d0-ed09-4367-88ce-b68964511e76
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---

# 監控管理事件{#monitoring-administrative-events}

您應定期監控事件記錄檔以追蹤Insight Server系統事件訊息，這些訊息會記錄至`<YYYYMMDD>-event.txt`檔案，預設位於Insight Server安裝目錄內的「事件」資料夾中。

**建議頻率：** 每5-10分鐘

您可以使用[!DNL Insight]中的[!DNL Server Files Manager]、您的自動管理工具、[!DNL *-event.txt]檔案或Windows事件查看器來監視這些事件。

>[!NOTE]
>
>管理事件日誌與Windows事件日誌完全不同，但包含一些相同的事件。 管理事件日誌僅包含有關[!DNL Insight Server]事件的資訊。

**若要檢視events.txt檔案，請透過[!DNL Server Files Manager]**

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵活動[!DNL Insight Server]的表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Events]**&#x200B;以查看其內容。
1. 按一下右鍵所需檔案旁&#x200B;*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Temp]列中的檔案名旁會出現複選標籤。
1. 按一下右鍵[!DNL Temp]列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 事件檔案將出現在新的Microsoft Windows Notepad窗口中。

   ![步驟資訊](assets/vis_FileManager_eventfile.png)

   [!DNL Insight Server]安裝目錄內[!DNL Trace]資料夾中的[!DNL Server.log]檔案包含更詳細的記錄資訊。

**通過Windows事件查看器查看事件**

* 按一下「**[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**」。

**更改管理事件日誌目錄**

「管理事件日誌」配置檔案[!DNL Administrative Events Log.cfg]指定輸出事件日誌的目錄。

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。

1. 按一下右鍵要配置的[!DNL Insight Server]表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Administrative Event Logs.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Administrative Event Logs.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Administrative Event Logs.cfg]的[!DNL Temp]列中出現複選標籤。

1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。

1. 在[!DNL Administrative Event Logs.cfg]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。 預設路徑是[!DNL Insight Server]安裝目錄內的[!DNL Events]資料夾。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在Path參數中，鍵入要輸出事件日誌記錄資料的目錄的名稱。
1. 執行下列操作，將更改保存到伺服器：

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
   1. 在[!DNL Server Files Manager]中，按一下右鍵[!DNL Temp]列中檔案的複選標籤，然後選擇&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL server name]**。
