---
description: 編輯Log Processing.cfg檔案時要考慮的概念性資訊。
title: 記錄處理組態檔的考量事項
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
exl-id: 278a4a10-d382-4d9f-b3f4-bcc4783eb50c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# 記錄處理組態檔的考量事項{#considerations-for-the-log-processing-configuration-file}

編輯Log Processing.cfg檔案時要考慮的概念性資訊。

* 定義資料集的源後，不應在目錄之間移動資料檔案。 目錄應接收的唯一附加檔案是新建立的檔案，這些檔案是資料工作台伺服器從感測器接收資料後生成的。
* 若要變更此檔案中的任何參數，必須重新處理所有資料。 [!DNL Log Processing Mode.cfg]檔案中的「暫停」參數必須設為false，才能進行重新處理。 （請注意，此參數的預設值為false，因此可能不需要變更參數。） 有關[!DNL Log Processing Mode.cfg]檔案的資訊，請參見[其他配置檔案](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)。

* 如果您重新處理資料，可以在資料工作台的[!DNL Processing Legend]中檢查「記錄處理進度」參數。

   如需重新處理資料的詳細資訊，請參閱[重新處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。 請參閱[處理圖例](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828)。

* [!DNL Log Processing.cfg]檔案可由多個資料集描述檔共用。 在[!DNL Log Processing.cfg]檔案中定義的轉換將應用於共用此配置檔案的所有資料集配置檔案。

   >[!NOTE]
   >
   >Adobe建議在一個或多個日誌處理[!DNL dataset include]檔案中定義日誌處理的轉換。 如需詳細資訊，請參閱[記錄處理資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)。

* 通過在記事本中開啟和編輯檔案，可以將上述任何參數添加到[!DNL Log Processing.cfg]檔案中。 當您在資料工作台中重新開啟檔案時，您所做的任何變更和儲存都會出現。 添加新參數時，請使用空格鍵（而非Tab鍵）在前一個標題級別的右側縮進兩(2)個空格。

   在資料集構建過程的日誌處理階段中發生的任何資料集配置檔案錯誤都顯示在資料工作台的[!DNL Detailed Status]介面的[!DNL Profiles]節點中。 有關[!DNL Detailed Status]介面的資訊，請參閱&#x200B;*Data Workbench使用手冊*。
