---
description: 儀表板要從中視覺化資料的每個DPU都必須有查詢API授權。
solution: Analytics
title: 驗證查詢API啟用
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 驗證查詢API啟用{#verifying-query-api-enablement}

儀表板要從中視覺化資料的每個DPU都必須有查詢API授權。

以下說明如何驗證已安裝並啟用查詢API。

1. 尋找您的資料工作台伺服器憑證。
1. 在文字編輯器中開啟此憑證。
1. 請確定該行存 `Product = Query API` 在於證書中。
1. 在檔案 **[!UICONTROL Trace]** 夾中，在文本 [!DNL InsightServer64.log] 編輯器中開啟。
1. 在最新的啟動日誌條目中，確保顯示該 `Enabling Query API (licensed)` 行。

* 如果未啟用查詢API，您會看到該項目 `Not enabling Query API (not licensed)`。
* 如果您未看到任何日誌條目，或懷疑自添加查詢API以來資料工作台伺服器已重新啟動，請重新啟動資料工作台伺服器並檢查日誌。

   如果您無法驗證查詢API是否已啟用，請聯絡Adobe ClientCare以取得協助。
