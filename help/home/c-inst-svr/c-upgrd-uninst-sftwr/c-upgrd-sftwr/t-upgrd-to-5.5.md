---
description: 從5.4安裝升級6.1Data Workbench的伺服器元件。
title: DWB Server 5.4至5.5升級版
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB 伺服器升級：5.4 升級至 5.5{#dwb-server-upgrade-to}

從5.4安裝升級6.1Data Workbench的伺服器元件。

因此，從[!DNL Insight] 5.4升級到[!DNL Insight] 5.5相對簡單。

您也可以使用以下步驟，直接從[!DNL Insight] 5.3升級至[!DNL Insight] 5.5。 請確定您執行[從Insight 5.4升級至5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)區段和[從Insight 5.4升級至5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9)區段中列出的所有升級工作。

1. 停止群集中除[!DNL Insight Master Server]外所有伺服器上的[!DNL Insight Server]服務。

   1. 將新的[!DNL ReportServer.exe]和[!DNL Insight.exe]檔案複製到Software\Insight資料夾。

   1. 在[!DNL Insight]客戶端更新後，將[!DNL InsightServer.exe]和[!DNL InsightServer64.exe]檔案複製到\Bin資料夾。

   1. 等待[!DNL Insight Master Server]啟動，然後驗證透過[!DNL Connections]視覺化執行的版本。

1. 在[!DNL Insight]用戶端的叢集[!DNL Master Server]上：

   1. 建立現有[!DNL Base]配置檔案的本地副本並對其進行更名（例如，BaseBackup）。
   1. 將新的[!DNL Base]配置檔案複製到Profiles資料夾。
   1. 對「轉換」資料夾重複這兩個步驟。

1. 將Scripts資料夾從伺服器包複製到[!DNL Master Server]中的Server安裝目錄。
1. 將[!DNL Terrain Images.cfg.off]檔案複製到[!DNL Master Server]的「元件」資料夾中。
   **將客戶端軟體從 [!DNL Insight] 5.4升級到5.5**

在[!DNL Insight.cfg]檔案中，請確定「更新軟體」設定已設為TRUE。
