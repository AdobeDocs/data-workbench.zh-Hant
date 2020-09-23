---
description: 稽核記錄檔會追蹤所有嘗試連線至Insight Server和從Insight Server斷開的連線，每個連線都記錄在<YYYYMMDD>-access.txt檔案中，預設位於Insight Server安裝目錄的「稽核」資料夾中。
solution: Analytics
title: 監控稽核記錄
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---


# 監控稽核記錄{#monitoring-audit-logs}

稽核記錄檔會追蹤所有嘗試連線至Insight Server和從Insight Server斷開的連線，每個連線都記錄在Insight Server安裝目錄中，預設位於「稽核」資料夾的檔案中。 `<YYYYMMDD>-access.txt`

**建議頻率：** 每日或視需要進行疑難排解

當疑難排解連接至的問題時，稽核記錄檔會非常有用 [!DNL Insight Server]。 您可以使用自動化管理工具或直接檢視檔案來監控這 [!DNL access.txt] 些記錄檔。

**若要透過[!DNL Server Files Manager]**

1. 在「 [!DNL Insight]>」標籤 [!DNL Admin] 中， [!DNL Dataset and Profile] 按一下縮圖以開 **[!UICONTROL Servers Manager]** 啟「伺服器管理員」工作區。
1. 按一下右鍵活動表徵圖，然 [!DNL Insight Server] 後按一下 **[!UICONTROL Server Files]**。
1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Audit]** 查看其內容。
1. 按一下右鍵所需檔案旁 *的伺服器名稱列* ，然後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在欄中的檔案名稱旁 [!DNL Temp] 邊。
1. 在欄中按一下新核取標籤， [!DNL Temp] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 審計日誌將顯示在新的Microsoft Windows Notepad窗口中。

   ![步驟資訊](assets/cfg_accesscontrol_accessFile.png)

