---
description: 您應定期監控事件記錄檔以追蹤Insight Server系統事件訊息，這些訊息會記錄在Insight Server安裝目錄內「事件」資料夾中預設的<YYYYMMDD>-event.txt檔案中。
solution: Analytics
title: 監控管理事件
uuid: 92d71478-0857-4af8-909c-0cf800b081f4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 2%

---


# 監控管理事件{#monitoring-administrative-events}

您應定期監控事件記錄檔，以追蹤Insight Server系統事件訊息，這些訊息會記錄在Insight Server安裝目錄內 `<YYYYMMDD>-event.txt` 「事件」資料夾中，預設位於檔案中。

**建議頻率：** 每5-10分鐘

您可以使用中、自動管 [!DNL Server Files Manager] 理工 [!DNL Insight]具、檔案或Windows事 [!DNL *-event.txt] 件查看器來監視這些事件。

>[!NOTE]
>
>管理事件日誌與Windows事件日誌完全不同，但包含一些相同的事件。 「管理事件記錄檔」僅包含有關事件的 [!DNL Insight Server] 資訊。

**若要透過[!DNL Server Files Manager]**

1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。
1. 按一下右鍵活動表徵圖，然 [!DNL Insight Server] 後按一下 **[!UICONTROL Server Files]**。
1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Events]** 查看其內容。
1. 按一下右鍵所需檔案旁 *的伺服器名稱列* ，然後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在欄中的檔案名稱旁 [!DNL Temp] 邊。
1. 在欄中按一下滑鼠右鍵， [!DNL Temp] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 事件檔案將出現在新的Microsoft Windows Notepad窗口中。

   ![步驟資訊](assets/vis_FileManager_eventfile.png)

   安裝 [!DNL Server.log] 目錄內 [!DNL Trace] 資料夾中的 [!DNL Insight Server] 檔案包含更詳細的記錄資訊。

**若要透過Windows事件檢視器檢視事件**

* Click **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**.

**更改管理事件日誌目錄**

管理事件日誌配置檔案 [!DNL Administrative Events Log.cfg]指定將事件記錄輸出到的目錄。

1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。

1. 按一下右鍵要配置的 [!DNL Insight Server] 表徵圖，然後按一下 **[!UICONTROL Server Files]**。

1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Components]** 查看其內容。 文 [!DNL Administrative Event Logs.cfg] 件位於此目錄中。

1. 按一下右鍵的伺服器名 *稱列中的複選標籤* ，然 [!DNL Administrative Event Logs.cfg] 後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在的 [!DNL Temp] 列中 [!DNL Administrative Event Logs.cfg]。

1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。

1. 在視窗 [!DNL Administrative Event Logs.cfg] 中，按一 **[!UICONTROL component]** 下以檢視其內容。 預設路徑是安 [!DNL Events] 裝目錄內 [!DNL Insight Server] 的資料夾。

   ![](assets/cfg_adminevents_examplevalues.png)

1. 在路徑參數中，鍵入要輸出事件記錄資料的目錄的名稱。
1. 執行下列動作，將變更儲存至伺服器：

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。
   1. 在中， [!DNL Server Files Manager]按一下右鍵列中檔案的複選標籤，然 [!DNL Temp] 後選擇 **[!UICONTROL Save to]** > **[!UICONTROL server name]**。

