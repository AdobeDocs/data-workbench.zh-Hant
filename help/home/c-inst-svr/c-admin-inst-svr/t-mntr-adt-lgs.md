---
description: 稽核記錄檔會追蹤所有嘗試連線至Insight Server和從Insight Server斷開的連線，每個連線都記錄在<YYYYMMDD>-access.txt檔案中，預設位於Insight Server安裝目錄的「稽核」資料夾中。
title: 監控稽核記錄
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# 監控稽核記錄{#monitoring-audit-logs}

稽核記錄檔會追蹤所有嘗試連線至Insight Server和從Insight Server中斷連線的動作，每個連線都記錄在`<YYYYMMDD>-access.txt`檔案中，預設位於Insight Server安裝目錄的「稽核」資料夾中。

**建議的頻率：** 每日或視需要進行疑難排解

當疑難排解連接至[!DNL Insight Server]的問題時，審核日誌非常有用。 您可以使用自動化管理工具或直接檢視[!DNL access.txt]檔案來監控這些記錄檔。

**若要透過[!DNL Server Files Manager]**

1. 在[!DNL Insight]的[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵活動[!DNL Insight Server]的表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Audit]**&#x200B;查看其內容。
1. 按一下右鍵所需檔案旁&#x200B;*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Temp]欄中，檔案名稱旁會出現複選標籤。
1. 在[!DNL Temp]欄中按一下新核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 審計日誌將顯示在新的Microsoft Windows Notepad窗口中。

   ![步驟資訊](assets/cfg_accesscontrol_accessFile.png)
