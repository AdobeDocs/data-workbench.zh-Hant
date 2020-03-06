---
description: 繼承配置檔案的轉換資料集包含檔案包含與資料集構建的轉換階段相關聯的參數。
solution: Analytics
title: 轉換資料集包含檔案
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 轉換資料集包含檔案{#transformation-dataset-include-files}

繼承配置檔案的轉換資料集包含檔案包含與資料集構建的轉換階段相關聯的參數。

檔案的第一行定義了支援「擴 [!DNL TransformationInclude] 展尺寸」(Extended Dimensions)、「參數」(Parameters)、「重新處理」(Reprocess)、「舞台」(Stage)和「變形」(Transformations)參數的類型。 所有其他參數必須在資料集描述檔 [!DNL Transformation.cfg] 的「資料集」目錄的檔案中定義。

在檔案中包括擴展尺寸、參數、重新處理、舞台和轉換以外的參 [!DNL Transformation Dataset Include] 數會生成錯誤。

您可以為檔案 [!DNL Transformation Dataset Include] 命名任何項目，但其副檔名必須為 [!DNL .cfg]。 檔案必須儲存在繼承的描述檔名 *稱\Dataset\Transformation directory中*。 由於檔案是在資料集建構的轉換階段以遞歸方式載入，因此您可以將檔案儲存在目錄中的任何層級(例如，繼承的描述檔名稱 [!DNL Transformation Dataset Include]**\Dataset\Transformation\*檔案夾名稱*\*include file name*.cfg)。

>[!NOTE]
>
>許多網站的特定Web組態參數都在檔案中 [!DNL Transformation Dataset Include] 定義。 如需這些參數的詳細資訊，請參 [閱Web資料的組態設定](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

下表說明檔案中可用的參 [!DNL Transformation Dataset Include] 數：

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 延伸尺寸 </td> 
   <td colname="col2"> 選填。定義擴展尺寸。 請參閱 <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 延伸維度</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參數 </td> 
   <td colname="col2"> 選填。可在其他配置參數中引用的變數。 如需詳細資訊，請參 <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 閱「在資料集中定義參數包含檔案」</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新處理 </td> 
   <td colname="col2"> <p>選填。您可在此處輸入任何字元或字元組合。 更改此參數並保存檔案會啟動資料重新轉換。 </p> <p> 如需重新處理資料的詳細資訊，請參閱重新 <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 處理和重新轉換</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>選填。套用至此轉換資料集包含檔案的處 <span class="wintitle"> 理階段的名稱</span> 。 處理階段是在 <span class="filepath"> Transformation.cfg檔案的「階段」參數中定義</span> 。 </p> <p> <p>注意：當您指定舞台時，舞台的名稱必須與資料集描述檔的 <span class="filepath"></span> Transformation.cfg檔案中Stages參數中所列的名稱完全相符。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 轉換 </td> 
   <td colname="col2"> 選填。定義轉換期間需要應用的資料轉換。 有關可用轉換類型的資訊，請參 <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 閱資料轉換</a>。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有關檔案中參數的說明，請 [!DNL Transformation.cfg] 參見轉 [換配置檔案](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)。

當您使用檔案時，應牢記下列 [!DNL Transformation Dataset Include] 點：

* 變更此檔案中的任何參數需要重新轉換資料。
* [!DNL CrossRows]、、 [!DNL ODBCLookup]、 [!DNL Sessionize]和 [!DNL AppendURI] 轉換僅在檔案中定義時才可 [!DNL Transformation Dataset Configuration] 用。 有關這些轉換的資訊，請參 [閱資料轉換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

* 通過在記事本中開啟和編輯檔案，可 [!DNL Transformation Dataset Include] 以將上述任何參數添加到檔案中。 當您在資料工作台中重新開啟檔案時，您所做的任何變更和儲存都會出現。 添加新參數時，請使用空格鍵（而非Tab鍵）在前一個標題級別的右側縮進兩(2)個空格。

如果您訂閱Adobe或資 [!DNL IP Geo-location] 料 [!DNL IP Geo-intelligence] 服務，Adobe會提供您內部描述檔，其中包含一組資料轉換和延伸維度，這些維度是專為資料服務而建立。 轉換和維定義在內部 [!DNL Transformation Dataset Include] 配置檔案的「資料集」目錄中的檔案中。 如需安裝或資料服務內部設定檔的 [!DNL IP Geo-location] 指示 [!DNL IP Geo-intelligence] ，請參閱資 *料工作台使用指南*。
