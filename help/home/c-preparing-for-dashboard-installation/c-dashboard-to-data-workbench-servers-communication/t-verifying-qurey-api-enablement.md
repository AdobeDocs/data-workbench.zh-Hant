---
description: 控制面板要視覺化資料的每個DPU都必須具備查詢API授權。
title: 驗證查詢 API 啟用
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# 驗證查詢 API 啟用{#verifying-query-api-enablement}

控制面板要視覺化資料的每個DPU都必須具備查詢API授權。

以下是如何驗證Query API是否已安裝及啟用的一些指示。

1. 尋找您的Data Workbench伺服器憑證。
1. 在文字編輯器中開啟此憑證。
1. 確認憑證中存在`Product = Query API`行。
1. 在&#x200B;**[!UICONTROL Trace]**&#x200B;資料夾中，在文字編輯器中開啟[!DNL InsightServer64.log]。
1. 在最新的啟動日誌條目中，確保顯示`Enabling Query API (licensed)`行。

* 如果未啟用查詢API，您會看到`Not enabling Query API (not licensed)`項目。
* 如果您沒有看見任何記錄項目，或懷疑Data Workbench伺服器自新增查詢API後已重新啟動，請再次重新啟動Data Workbench伺服器並檢查記錄檔。

   如果您無法驗證是否已啟用查詢API，請聯絡AdobeClientCare以取得協助。
