---
description: 安裝Insight Server FSU及將其設定為管理用途的指示與安裝及設定Insight Server DPU的指示非常類似。
title: Insight Server FSU 的安裝程序
uuid: ffed5095-f83c-4641-9ccc-4b94f51c3f95
exl-id: 7373af97-0ecf-47a2-bc27-dbfeb7ca3eaa
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 8%

---

# Insight Server FSU 的安裝程序{#installation-procedures-for-an-insight-server-fsu}

安裝Insight Server FSU及將其設定為管理用途的指示與安裝及設定Insight Server DPU的指示非常類似。

對於Windows 2012伺服器中的&#x200B;*MS System Center端點保護*，這些執行檔需要添加到&#x200B;**排除的進程：**

* [!DNL InsightServer64.exe]
* [!DNL ReportServer.exe]
* [!DNL ExportIntegration.exe]

要安裝和配置[!DNL Insight Server] FSU，必須完成以下任務：

1. 安裝[!DNL Insight Server]程式檔案。
1. 安裝[!DNL Insight Server]數位憑證。
1. 檢查[!DNL Communications.cfg]檔案中的埠設定。
1. 修改[!DNL Access Control.cfg]檔案，以允許從[!DNL the Client]對[!DNL the Server]進行管理訪問。
1. 修改[!DNL server.address]檔案以定義伺服器的網路位置。
1. 按說明設定Windows記憶體使用參數。
1. 按照說明將[!DNL Insight Server]註冊為Windows服務。

   有關為[!DNL Insight Server] FSU配置資料源、權限和通信的說明，請參閱&#x200B;*資料集配置指南*。
