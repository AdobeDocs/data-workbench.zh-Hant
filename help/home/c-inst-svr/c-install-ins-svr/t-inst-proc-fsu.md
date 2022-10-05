---
description: 安裝Insight Server FSU及將其設定為管理用途的指示，與安裝及設定Insight Server DPU的指示非常類似。
title: Insight Server FSU 的安裝程序
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Insight Server FSU 的安裝程序{#installation-procedures-for-an-insight-server-fsu}

{{eol}}

安裝Insight Server FSU及將其設定為管理用途的指示，與安裝及設定Insight Server DPU的指示非常類似。

針對 *MS System Center Endpoint Protection* 在Windows 2012伺服器中，這些執行檔需要添加到 **排除的進程：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

若要安裝和設定 [!DNL Insight Server] FSU，您必須完成下列工作：

1. 安裝 [!DNL Insight Server] 程式檔案。
1. 安裝 [!DNL Insight Server] 數位憑證。
1. 檢查 [!DNL Communications.cfg] 檔案。
1. 修改 [!DNL Access Control.cfg] 允許管理訪問的檔案 [!DNL the Server] 從 [!DNL the Client].
1. 修改 [!DNL server.address] 檔案來定義伺服器的網路位置。
1. 按說明設定Windows記憶體利用率參數。
1. 註冊 [!DNL Insight Server] 作為Windows服務，如所述。

   針對 [!DNL Insight Server] FSU，看 *資料集組態指南*.
