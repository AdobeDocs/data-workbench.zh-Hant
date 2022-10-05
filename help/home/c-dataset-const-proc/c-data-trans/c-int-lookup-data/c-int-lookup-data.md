---
description: Data Workbench提供一組轉換，可讓Data Workbench伺服器將查閱資料併入資料集。
title: 整合查閱資料
uuid: 35fd48f7-c0c4-4a83-919d-c15902f27495
exl-id: 150d3aae-4431-488f-8f19-b522637ee935
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# 整合查閱資料{#integrating-lookup-data}

{{eol}}

Data Workbench提供一組轉換，可讓Data Workbench伺服器將查閱資料併入資料集。

查詢資料是來自公司資料庫或查詢檔案的外部資料，可與事件資料結合以建立資料集。 一般而言，您會使用查詢資料來增加來自記錄來源的事件資料。 從概念上講，您可以考慮使用查閱資料，將事件資料記錄填入其他資訊欄。

使用查閱資料時，會將資料載入記憶體駐留查閱表格中。 表格中的欄必須包含事件資料記錄中也存在的共同索引鍵。 查閱表本身中的資料可從普通檔案或ODBC資料源中載入。 在資料集建構程式的記錄處理或轉換階段期間，查詢資料可併入資料集。

若要合併查詢資料，您必須先產生查詢檔案或具有存取SQL資料庫所需的資訊，然後在資料集組態檔中定義下列一或多個轉換，以進行記錄處理和轉換。

**將查詢資料整合至資料集**

1. 產生查詢檔案。 請參閱 [填入查閱表格](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-pop-lookup-table.md#concept-dd761338731a40e0997c33dfdabdcdf8).
1. 在適當資料集組態檔的「轉換」參數中，定義下列其中一種轉換類型：

   * [!DNL Categorize]
   * [!DNL FlatFileLookup]
   * [!DNL ODBCLookup]

>[!NOTE]
>
>請注意， [!DNL ODBCLookup] 轉換只有在 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案。
