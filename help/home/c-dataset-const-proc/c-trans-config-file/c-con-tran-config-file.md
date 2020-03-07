---
description: 編輯Transformation.cfg檔案時要考慮的重要資訊。
solution: Analytics
title: 轉換配置檔案的注意事項
topic: Data workbench
uuid: 1b64d023-966d-4f84-beb6-4f02b3504eea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 轉換配置檔案的注意事項{#considerations-for-the-transformation-configuration-file}

編輯Transformation.cfg檔案時要考慮的重要資訊。

* 變更此檔案中的任何參數需要重新轉換資料。
* 如果您重新處理資料，則可以在資 [!DNL Transformation Progress] 料工作台中檢查參數 [!DNL Processing Legend]。

   如需重新處理資料的詳細資訊，請參 [!DNL Processing Legend,] 閱重新 [處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL CrossRows]、、 [!DNL ODBCLookup]、 [!DNL Sessionize]和 [!DNL AppendURI] 轉換僅在檔案中定義時才可 [!DNL Transformation Dataset Configuration] 用。 有關這些轉換的資訊，請參 [閱資料轉換](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

   >[!NOTE]
   >
   >Adobe建議在一或多個檔案中定義資料集建構的轉換階 [!DNL Transformation Dataset Include] 段。 如需詳細資訊，請參 [閱轉換資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。

* 通過在記事本中開啟和編輯檔案，可 [!DNL Transformation.cfg] 以將上述任何參數添加到檔案中。 當您在資料工作台中重新開啟檔案時，您所做的任何變更和儲存都會出現。 添加新參數時，請使用空格鍵（而非Tab鍵）在前一個標題級別的右側縮進兩(2)個空格。

   在資料集構建過程的資料集轉換階段期間發生的任何錯誤都顯示在資料 [!DNL Profiles] 工作台的接 [!DNL Detailed Status] 口節點中。 如需介面的詳 [!DNL Detailed Status] 細資訊，請參 *閱資料工作台使用指南*。

