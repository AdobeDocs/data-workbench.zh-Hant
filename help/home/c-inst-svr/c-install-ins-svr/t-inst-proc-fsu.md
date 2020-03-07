---
description: 安裝Insight Server FSU及將其設定為管理用途的指示與安裝及設定Insight Server DPU的指示非常類似。
solution: Insight
title: Insight Server FSU的安裝程式
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Server FSU的安裝程式{#installation-procedures-for-an-insight-server-fsu}

安裝Insight Server FSU及將其設定為管理用途的指示與安裝及設定Insight Server DPU的指示非常類似。

對於 *Windows 2012伺服器中的MS System Center端點保護* ，這些執行檔需要添加到排除的 **進程中：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

要安裝和配置 [!DNL Insight Server] FSU，必須完成以下任務：

1. 安裝程 [!DNL Insight Server] 序檔案。
1. 安裝數 [!DNL Insight Server] 位憑證。
1. 檢查檔案中的埠 [!DNL Communications.cfg] 設定。
1. 修改文 [!DNL Access Control.cfg] 件，允許管理訪問 [!DNL the Server] 自 [!DNL the Client]。
1. 修改檔 [!DNL server.address] 案以定義伺服器的網路位置。
1. 按說明設定Windows記憶體使用參數。
1. 如 [!DNL Insight Server] 所述註冊為Windows服務。

   如需為 [!DNL Insight Server] FSU設定資料來源、權限和通訊的指示，請參閱資料集 *設定指南*。

