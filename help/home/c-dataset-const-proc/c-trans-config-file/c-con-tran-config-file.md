---
description: 編輯Transformation.cfg檔案時應考慮的重要資訊。
title: 轉換組態檔的考量事項
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# 轉換組態檔的考量事項{#considerations-for-the-transformation-configuration-file}

編輯Transformation.cfg檔案時應考慮的重要資訊。

* 變更此檔案中的任何參數都需要重新轉換資料。
* 如果您重新處理資料，可以檢查Data Workbench的[!DNL Processing Legend]中的[!DNL Transformation Progress]參數。

   有關重新處理資料或[!DNL Processing Legend,]的資訊，請參閱[重新處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL CrossRows]、 、  [!DNL ODBCLookup]、  [!DNL Sessionize] [!DNL AppendURI] 和轉換只有在檔案中定義時才 [!DNL Transformation Dataset Configuration] 有效。有關這些轉換的資訊，請參閱[資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

   >[!NOTE]
   >
   >Adobe建議在一個或多個[!DNL Transformation Dataset Include]檔案中定義資料集建構的轉換階段的轉換。 如需詳細資訊，請參閱[轉換資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。

* 您可以在記事本中開啟並編輯檔案，將上述任何參數添加到[!DNL Transformation.cfg]檔案中。 當您在Data Workbench中重新開啟檔案時，您所做和儲存的任何變更都會顯示。 添加新參數時，使用空格鍵（而非Tab鍵）縮進前一個標題級別右側的兩(2)個空格。

   資料集設定檔的資料集建構程式在轉換階段期間發生的任何錯誤，都會顯示在Data Workbench中[!DNL Detailed Status]介面的[!DNL Profiles]節點中。 有關[!DNL Detailed Status]介面的資訊，請參閱&#x200B;*Data Workbench使用手冊*。
