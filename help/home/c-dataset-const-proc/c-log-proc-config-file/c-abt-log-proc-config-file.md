---
description: Log Processing.cfg檔案控制資料集建構的記錄處理階段，期間會從資料來源（稱為記錄來源）讀取無序資料，並套用篩選和轉換至資料。
title: 關於記錄處理組態檔
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# 關於記錄處理組態檔{#about-the-log-processing-configuration-file}

Log Processing.cfg檔案控制資料集建構的記錄處理階段，期間會從資料來源（稱為記錄來源）讀取無序資料，並套用篩選和轉換至資料。

您必須編輯[!DNL Log Processing.cfg]檔案，才能執行下列任何資料集設定工作：

* 指定日誌源。 請參閱[記錄來源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md)。
* 確定哪些日誌條目在日誌處理期間輸入資料集。 請參閱[資料篩選](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)和[記錄項目條件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)。

* 啟用大量事件資料的追蹤ID分割。 請參閱[鍵拆分](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md)。
* 將資料工作台伺服器配置為作為檔案伺服器單元運行。 請參閱[設定Insight Server檔案伺服器裝置](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。
* 將資料工作台伺服器設定為以集中式標準化伺服器執行。 請參閱[設定Insight Server檔案伺服器裝置](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] 檔案可以包含資料集構建日誌處理階段的其它說明。這些檔案存在於任何繼承的配置檔案的「資料集\日誌處理」目錄中。 它們通常會定義應用程式特定參數（例如網站應用程式的網頁特定組態參數）。 有關[!DNL Log Processing Dataset Include]檔案的資訊，請參見[資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。 如需網站特定Web組態參數的詳細資訊，請參閱[網站資料的組態設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md)。
