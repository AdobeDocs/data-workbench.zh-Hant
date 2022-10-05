---
description: 從5.4安裝升級Data Workbench6.1的伺服器元件。
title: DWB伺服器升級5.4至5.5
uuid: 9cf9f493-f098-4c6d-a8b5-786833496557
exl-id: dd8c2a89-6a40-4ebf-a964-eb4851ab94a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# DWB 伺服器升級：5.4 升級至 5.5{#dwb-server-upgrade-to}

{{eol}}

從5.4安裝升級Data Workbench6.1的伺服器元件。

因此，從 [!DNL Insight] 5.4至 [!DNL Insight] 5.5相對簡單。

您也可以直接從 [!DNL Insight] 5.3至 [!DNL Insight] 5.5使用下列步驟。 請務必執行 [從Insight 5.4升級至5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 區段和 [從Insight 5.4升級至5.5](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/t-upgrd-to-5.5.md#task-b581e47952e941158d52db3e68f076b9) 區段。

1. 停止 [!DNL Insight Server] 群集中所有伺服器上的服務( [!DNL Insight Master Server].

   1. 複製新 [!DNL ReportServer.exe] 和 [!DNL Insight.exe] 檔案到「軟體\分析」資料夾。

   1. 在 [!DNL Insight] 客戶端已更新，請複製 [!DNL InsightServer.exe] 和 [!DNL InsightServer64.exe] 檔案放入\Bin資料夾。

   1. 等待 [!DNL Insight Master Server] 若要開始，請驗證透過 [!DNL Connections] 視覺效果。

1. 群集上 [!DNL Master Server] 在 [!DNL Insight] 用戶端：

   1. 製作現有 [!DNL Base] 配置檔案並更名它（例如BaseBackup）。
   1. 複製新 [!DNL Base] 配置檔案到配置檔案資料夾。
   1. 對「轉換」資料夾重複這兩個步驟。

1. 將指令碼資料夾從伺服器套件複製到 [!DNL Master Server] 到伺服器安裝目錄。
1. 複製 [!DNL Terrain Images.cfg.off] 檔案放入 [!DNL Master Server].
   **從升級客戶端軟體 [!DNL Insight] 5.4 - 5.5**

在 [!DNL Insight.cfg] 檔案中，確保「更新軟體」設定設定為TRUE。
