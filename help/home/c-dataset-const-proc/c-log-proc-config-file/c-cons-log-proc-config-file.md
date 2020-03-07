---
description: 編輯Log Processing.cfg檔案時要考慮的概念性資訊。
solution: Analytics
title: 日誌處理配置檔案的注意事項
topic: Data workbench
uuid: 2ccedf63-12d9-40e9-912a-aee030191b1e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 日誌處理配置檔案的注意事項{#considerations-for-the-log-processing-configuration-file}

編輯Log Processing.cfg檔案時要考慮的概念性資訊。

* 定義資料集的源後，不應在目錄之間移動資料檔案。 目錄應接收的唯一附加檔案是新建立的檔案，這些檔案是資料工作台伺服器從感測器接收資料後生成的。
* 若要變更此檔案中的任何參數，必須重新處理所有資料。 檔案中的「暫停」 [!DNL Log Processing Mode.cfg] 參數必須設為false，才能進行重新處理。 （請注意，此參數的預設值為false，因此可能不需要變更參數。）有關該檔案的信 [!DNL Log Processing Mode.cfg] 息，請參 [閱Additional Configuration Files](../../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)。

* 如果重新處理資料，則可以在資料工作台的「日誌處理進度」參數中選中 [!DNL Processing Legend]。

   如需重新處理資料的詳細資訊，請參 [閱重新處理和轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。 請參閱 [處理圖例](../../../home/c-get-started/c-admin-intrf/c-pro-lgd.md#concept-233e27c9c84c426f8c178a27cc7ff828)。

* 檔案 [!DNL Log Processing.cfg] 可由多個資料集描述檔共用。 檔案中定義的轉 [!DNL Log Processing.cfg] 換將應用於共用此配置檔案的所有資料集配置檔案。

   >[!NOTE]
   >
   >Adobe建議在一或多個記錄處理檔案中定義記錄處理的 [!DNL dataset include] 轉換。 如需詳細資訊，請參 [閱記錄處理資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)。

* 通過在記事本中開啟和編輯檔案，可 [!DNL Log Processing.cfg] 以將上述任何參數添加到檔案中。 當您在資料工作台中重新開啟檔案時，您所做的任何變更和儲存都會出現。 添加新參數時，請使用空格鍵（而非Tab鍵）在前一個標題級別的右側縮進兩(2)個空格。

   在資料集構建過程的資料集處理階段期間發生的資料集配置檔案的任何錯誤都顯示在資料 [!DNL Profiles] 工作台的接 [!DNL Detailed Status] 口節點中。 如需介面的詳 [!DNL Detailed Status] 細資訊，請參 *閱資料工作台使用指南*。

