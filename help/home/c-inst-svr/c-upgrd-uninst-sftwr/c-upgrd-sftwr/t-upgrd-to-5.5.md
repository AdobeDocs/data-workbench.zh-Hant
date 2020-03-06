---
description: 從5.4安裝升級Data Workbench 6.1的伺服器元件。
solution: Insight
title: DWB Server 5.4至5.5升級版
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB伺服器升級：5.4至5.5{#dwb-server-upgrade-to}

從5.4安裝升級Data Workbench 6.1的伺服器元件。

因此，從 [!DNL Insight] 5.4升級到 [!DNL Insight] 5.5比較簡單。

您也可以使用下 [!DNL Insight] 列步驟，直接從 [!DNL Insight] 5.3升級至5.5。 請確定您執行「從Insight 5.4升級至5.5 [」區段和「從Insight 5.4升級至5.5」](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 區段中列出的所有升級工作 [](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 。

1. 停止群 [!DNL Insight Server] 集中除的所有伺服器上的服務 [!DNL Insight Master Server]。

   1. 將新檔案 [!DNL ReportServer.exe] 和文 [!DNL Insight.exe] 件複製到Software\Insight資料夾。

   1. 客戶 [!DNL Insight] 端更新後，將和文 [!DNL InsightServer.exe] 件復 [!DNL InsightServer64.exe] 制到\Bin資料夾。

   1. 等待開 [!DNL Insight Master Server] 始，然後驗證透過視覺化執行的版 [!DNL Connections] 本。

1. 在用戶端的叢 [!DNL Master Server] 集上 [!DNL Insight] :

   1. 製作現有配置檔案的本 [!DNL Base] 地副本並將其更名（例如BaseBackup）。
   1. 將新配置文 [!DNL Base] 件複製到「配置檔案」資料夾。
   1. 對「轉換」資料夾重複這兩個步驟。

1. 將Scripts資料夾從伺服器包複製到 [!DNL Master Server] 伺服器安裝目錄。
1. 將檔案 [!DNL Terrain Images.cfg.off] 複製到的「元件」資料夾中 [!DNL Master Server]。
   **將客戶端軟體從[!DNL Insight]5.4升級到5.5**

在檔 [!DNL Insight.cfg] 案中，請確定「更新軟體」設定為TRUE。
