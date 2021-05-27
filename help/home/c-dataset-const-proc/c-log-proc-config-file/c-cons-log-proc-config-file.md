---
description: 編輯Log Processing.cfg檔案時要考慮的概念資訊。
title: 記錄處理組態檔的考量事項
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# 記錄處理組態檔的考量事項{#considerations-for-the-log-processing-configuration-file}

編輯Log Processing.cfg檔案時要考慮的概念資訊。

* 定義資料集的來源後，不應在目錄之間移動資料檔案。 目錄應接收的唯一其他檔案是新建立的檔案，這些檔案是從Data Workbench伺服器接收來自感測器的資料所產生。
* 若要變更此檔案中的任何參數，必須重新處理所有資料。 [!DNL Log Processing Mode.cfg]檔案中的Pause參數必須設為false，才會進行重新處理。 （請注意，此參數的預設值為false，因此可能不需要變更參數。） 有關[!DNL Log Processing Mode.cfg]檔案的資訊，請參閱[其他配置檔案](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)。

* 如果您重新處理資料，可以檢查Data Workbench的[!DNL Processing Legend]中的「記錄處理進度」參數。

   如需重新處理資料的詳細資訊，請參閱[重新處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。 請參閱[處理圖例](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828)。

* [!DNL Log Processing.cfg]檔案可由多個資料集設定檔共用。 [!DNL Log Processing.cfg]檔案中定義的轉換會套用至共用此設定檔案的所有資料集設定檔。

   >[!NOTE]
   >
   >Adobe建議在一個或多個日誌處理[!DNL dataset include]檔案中定義日誌處理的轉換。 如需詳細資訊，請參閱[記錄處理資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)。

* 您可以在記事本中開啟並編輯檔案，將上述任何參數添加到[!DNL Log Processing.cfg]檔案中。 當您在Data Workbench中重新開啟檔案時，您所做和儲存的任何變更都會顯示。 添加新參數時，使用空格鍵（而非Tab鍵）縮進前一個標題級別右側的兩(2)個空格。

   資料集設定檔的資料集建構程式在記錄處理階段期間發生的任何錯誤，都會顯示在Data Workbench中[!DNL Detailed Status]介面的[!DNL Profiles]節點中。 有關[!DNL Detailed Status]介面的資訊，請參閱&#x200B;*Data Workbench使用手冊*。
