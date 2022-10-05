---
description: 稽核記錄檔會追蹤所有嘗試連線至Insight Server及從Insight Server中取消連線的動作，且每個連線都記錄在 <yyyymmdd>-access.txt檔案，預設位於Insight Server安裝目錄內的「稽核」資料夾中。
title: 監控稽核記錄
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# 監控稽核記錄{#monitoring-audit-logs}

{{eol}}

稽核記錄檔會追蹤所有嘗試連線至Insight Server及從Insight Server中取消連線的動作，且每個連線都記錄在 `<YYYYMMDD>-access.txt` 檔案，預設位於Insight Server安裝目錄的稽核資料夾中。

**建議頻率：** 疑難排解的每日或視需要

在疑難排解連線的問題時，稽核記錄非常實用 [!DNL Insight Server]. 您可以使用自動管理工具或檢視 [!DNL access.txt] 檔案。

**若要檢視access.txt檔案，請透過[!DNL Server Files Manager]**

1. 在 [!DNL Insight]，在 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟「伺服器管理器」工作區。
1. 以滑鼠右鍵按一下作用中的圖示 [!DNL Insight Server] 按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Audit]** 來檢視其內容。
1. 以滑鼠右鍵按一下 *伺服器名稱* 欄，然後按一下 **[!UICONTROL Make Local]**. 中的檔案名稱旁會出現勾選記號 [!DNL Temp] 欄。
1. 以滑鼠右鍵按一下 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 稽核記錄會顯示在新的Microsoft Windows Notepad視窗中。

   ![步驟資訊](assets/cfg_accesscontrol_accessFile.png)
