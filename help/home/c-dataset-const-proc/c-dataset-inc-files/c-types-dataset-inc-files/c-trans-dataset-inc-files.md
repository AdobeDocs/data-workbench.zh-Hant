---
description: 繼承配置檔案的轉換資料集包含檔案包含與資料集構建的轉換階段相關聯的參數。
title: 轉換資料集包含檔案
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# 轉換資料集包含檔案{#transformation-dataset-include-files}

繼承配置檔案的轉換資料集包含檔案包含與資料集構建的轉換階段相關聯的參數。

檔案的第一行定義了支援擴展Dimension、參數、重新處理、舞台和轉換參數的類型[!DNL TransformationInclude]。 所有其他參數必須在資料集描述檔的Dataset目錄的[!DNL Transformation.cfg]檔案中定義。

在[!DNL Transformation Dataset Include]檔案中包括擴展Dimension、參數、重新處理、舞台和轉換以外的參數會生成錯誤。

您可以為[!DNL Transformation Dataset Include]檔案命名任何您想要的檔案，但其副檔名必須為[!DNL .cfg]。 檔案必須儲存在&#x200B;*繼承的配置檔案名*\Dataset\Transformation directory中。 由於檔案在資料集構建的轉換階段以遞歸方式載入，因此可以在目錄內的任何級別儲存[!DNL Transformation Dataset Include]檔案(例如，*繼承的配置檔案名*\Dataset\Transformation\*folder name*\*include file name*.cfg)。

>[!NOTE]
>
>[!DNL Transformation Dataset Include]檔案中定義了許多網站的特定Web組態參數。 有關這些參數的資訊，請參閱[ Configuration Settings for Web Data](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

下表說明[!DNL Transformation Dataset Include]檔案中可用的參數：

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 延伸維度 </td> 
   <td colname="col2"> 選填。定義擴展尺寸。 請參閱<a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md">擴展Dimension</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參數 </td> 
   <td colname="col2"> 選填。可在其他配置參數中引用的變數。 如需詳細資訊，請參閱<a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50">在資料集中定義參數包含檔案</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新處理 </td> 
   <td colname="col2"> <p>選填。您可在此處輸入任何字元或字元組合。 更改此參數並保存檔案會啟動資料重新轉換。 </p> <p> 如需重新處理資料的詳細資訊，請參閱<a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">重新處理和重新轉換</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>選填。應用於此<span class="wintitle">轉換資料集包含</span>檔案的處理階段的名稱。 處理階段在<span class="filepath"> Transformation.cfg</span>檔案的「階段」參數中定義。 </p> <p> <p>注意：指定舞台時，舞台的名稱必須與資料集描述檔的<span class="filepath"> Transformation.cfg</span>檔案中「舞台」參數中所列的名稱完全相符。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 轉換 </td> 
   <td colname="col2"> 選填。定義轉換期間需要應用的資料轉換。 有關可用轉換類型的資訊，請參閱<a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md">資料轉換</a>。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有關[!DNL Transformation.cfg]檔案中參數的說明，請參見[轉換配置檔案](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)。

使用[!DNL Transformation Dataset Include]檔案時，應牢記以下幾點：

* 變更此檔案中的任何參數需要重新轉換資料。
* [!DNL CrossRows]、、 [!DNL ODBCLookup]、 [!DNL Sessionize]和 [!DNL AppendURI] 轉換僅在檔案中定義時才 [!DNL Transformation Dataset Configuration] 起作用。有關這些轉換的資訊，請參見[資料轉換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

* 通過在記事本中開啟和編輯檔案，可以將上述任何參數添加到[!DNL Transformation Dataset Include]檔案中。 當您在資料工作台中重新開啟檔案時，您所做的任何變更和儲存都會出現。 添加新參數時，請使用空格鍵（而非Tab鍵）在前一個標題級別的右側縮進兩(2)個空格。

如果您訂閱Adobe的[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]資料服務，Adobe會提供您內部描述檔，其中包含一組資料轉換和為資料服務專門建立的延伸維度。 轉換和維定義在[!DNL Transformation Dataset Include]檔案中，這些檔案包含在內部配置檔案的Dataset目錄中。 有關安裝[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]資料服務內部配置檔案的說明，請參閱&#x200B;*Data Workbench使用手冊*。
