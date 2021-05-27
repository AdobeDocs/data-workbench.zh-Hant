---
description: 稽核記錄檔會追蹤所有嘗試連線至Insight Server及從Insight Server取消連線的動作，且每個連線都記錄在<YYYYMMDD>-access.txt檔案中，預設位於Insight Server安裝目錄內的「稽核」資料夾中。
title: 監控稽核記錄
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# 監控稽核記錄{#monitoring-audit-logs}

稽核記錄檔會追蹤所有嘗試連線至Insight Server及從Insight Server取消連線的動作，每個連線都記錄在`<YYYYMMDD>-access.txt`檔案中，預設位於Insight Server安裝目錄的「稽核」資料夾中。

**建議頻率：** 每日或視需要進行疑難排解

當疑難排解連線至[!DNL Insight Server]的問題時，稽核記錄會很有幫助。 您可以使用自動管理工具或直接檢視[!DNL access.txt]檔案來監控這些記錄。

**若要檢視access.txt檔案，請透過[!DNL Server Files Manager]**

1. 在[!DNL Insight]中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟「伺服器管理器」工作區。
1. 按一下右鍵活動[!DNL Insight Server]的表徵圖，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Audit]**&#x200B;以查看其內容。
1. 按一下右鍵所需檔案旁&#x200B;*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Temp]列中的檔案名旁會出現複選標籤。
1. 按一下右鍵[!DNL Temp]列中的新複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 審核日誌將顯示在新的Microsoft Windows Notepad窗口中。

   ![步驟資訊](assets/cfg_accesscontrol_accessFile.png)
