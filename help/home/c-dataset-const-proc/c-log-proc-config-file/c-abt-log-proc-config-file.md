---
description: Log Processing.cfg檔案控制資料集建構的記錄處理階段，在此期間，系統會從資料來源（即記錄來源）讀取未排序的資料，並將篩選和轉換套用至資料。
title: 關於記錄處理組態檔
uuid: 1f5f5d75-8a24-4122-adc8-8c8aef916631
exl-id: 11ee3298-272d-46c8-bcfe-e485b01606b1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 5%

---

# 關於記錄處理組態檔{#about-the-log-processing-configuration-file}

{{eol}}

Log Processing.cfg檔案控制資料集建構的記錄處理階段，在此期間，系統會從資料來源（即記錄來源）讀取未排序的資料，並將篩選和轉換套用至資料。

您必須編輯 [!DNL Log Processing.cfg] 檔案，以執行下列任何資料集設定任務：

* 指定日誌源。 請參閱 [記錄來源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md).
* 決定記錄處理期間要輸入資料集的記錄項目。 請參閱 [資料篩選](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md) 和 [記錄項目條件](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).

* 啟用將大量事件資料的追蹤ID拆分。 請參閱 [密鑰拆分](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md).
* 將Data Workbench伺服器設定為以檔案伺服器單元執行。 請參閱 [設定Insight Server檔案伺服器單元](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).
* 將Data Workbench伺服器設定為以集中式標準化伺服器執行。 請參閱 [設定Insight Server檔案伺服器單元](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

>[!NOTE]
>
>[!DNL Log Processing Dataset Include] 檔案可包含資料集建構之記錄處理階段的其他指示。 對於任何繼承的配置檔案，這些檔案都存在於資料集\日誌處理目錄中。 它們通常會定義應用程式專屬參數（例如網站應用程式的Web專屬設定參數）。 如需有關 [!DNL Log Processing Dataset Include] 檔案，請參閱 [資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). 如需Site的Web專屬設定參數相關資訊，請參閱 [Web資料的組態設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md).
