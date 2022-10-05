---
description: 編輯Transformation.cfg檔案時應考慮的重要資訊。
title: 轉換組態檔的考量事項
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
exl-id: 7164ccb5-269c-4968-a3b4-1ff046a57f92
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 5%

---

# 轉換組態檔的考量事項{#considerations-for-the-transformation-configuration-file}

{{eol}}

編輯Transformation.cfg檔案時應考慮的重要資訊。

* 變更此檔案中的任何參數都需要重新轉換資料。
* 如果您重新處理資料，可以檢查 [!DNL Transformation Progress] data workbench中的參數 [!DNL Processing Legend].

   如需重新處理資料或 [!DNL Processing Legend,] 請參閱 [重新處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]，和 [!DNL AppendURI] 只有在 [!DNL Transformation Dataset Configuration] 檔案。 如需這些轉換的相關資訊，請參閱 [資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

   >[!NOTE]
   >
   >Adobe建議在一或多個資料集建構的轉換階段中定義轉換 [!DNL Transformation Dataset Include] 檔案。 如需詳細資訊，請參閱 [轉換資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace).

* 您可以將上述任何參數新增至 [!DNL Transformation.cfg] 檔案，方法是在記事本中開啟和編輯檔案。 當您在Data Workbench中重新開啟檔案時，您所做和儲存的任何變更都會顯示。 添加新參數時，使用空格鍵（而非Tab鍵）縮進前一個標題級別右側的兩(2)個空格。

   在資料集建構程式的轉換階段期間，針對資料集設定檔發生的任何錯誤，都會顯示在 [!DNL Profiles] 節點 [!DNL Detailed Status] data workbench中的介面。 如需 [!DNL Detailed Status] 介面，請參閱 *Data Workbench使用手冊*.
