---
description: 資料工作台提供一組轉換，讓資料工作台伺服器將查閱資料併入資料集。
solution: Analytics
title: 整合查閱資料
topic: Data workbench
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 整合查閱資料{#integrating-lookup-data}

資料工作台提供一組轉換，讓資料工作台伺服器將查閱資料併入資料集。

查閱資料是來自公司資料庫或查閱檔案的外部資料，您可結合事件資料來建立資料集。 一般而言，您會使用查閱資料來增加來自記錄來源的事件資料。 從概念上講，您可以考慮使用查閱資料，將事件資料記錄填入其他資訊欄。

當您使用查閱資料時，會將資料載入駐留在記憶體中的查閱表格。 表中的列必須包含同樣存在於事件資料記錄中的公共鍵。 查閱表本身中的資料可以從平面檔案或ODBC資料源載入。 查閱資料可在資料集建構程式的記錄處理或轉換階段期間併入資料集。

要合併查找資料，必須首先生成查找檔案或具有訪問SQL資料庫所需的資訊，然後在資料集配置檔案中定義一個或多個用於日誌處理和轉換的以下轉換。

**若要將查閱資料整合至資料集**

1. 產生您的查閱檔案。 請參 [閱填入查閱表格](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8)。
1. 在適當的資料集配置檔案的「轉換」參數中定義下列轉換類型之一：

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>請注意，轉 [!DNL ODBCLookup] 換僅在檔案或檔案中定 [!DNL Transformation.cfg] 義時才可 [!DNL Transformation Dataset Include] 用。

