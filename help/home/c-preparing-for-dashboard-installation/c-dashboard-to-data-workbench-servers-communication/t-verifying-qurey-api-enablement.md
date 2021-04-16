---
description: 儀表板要從中視覺化資料的每個DPU都必須有查詢API授權。
title: 驗證查詢 API 啟用
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# 驗證查詢 API 啟用{#verifying-query-api-enablement}

儀表板要從中視覺化資料的每個DPU都必須有查詢API授權。

以下說明如何驗證已安裝並啟用查詢API。

1. 尋找您的資料工作台伺服器憑證。
1. 在文字編輯器中開啟此憑證。
1. 確保證書中存在行`Product = Query API`。
1. 在&#x200B;**[!UICONTROL Trace]**&#x200B;資料夾中，在文字編輯器中開啟[!DNL InsightServer64.log]。
1. 在最新的啟動日誌條目中，確保出現`Enabling Query API (licensed)`行。

* 如果未啟用查詢API，您將看到`Not enabling Query API (not licensed)`項目。
* 如果您未看到任何日誌條目，或懷疑自添加查詢API以來資料工作台伺服器已重新啟動，請重新啟動資料工作台伺服器並檢查日誌。

   如果您無法驗證查詢API是否已啟用，請聯絡AdobeClientCare以取得協助。
