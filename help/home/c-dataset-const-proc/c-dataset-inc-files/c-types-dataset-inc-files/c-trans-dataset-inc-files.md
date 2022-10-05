---
description: 繼承的設定檔的「轉換資料集包含」檔案包含與資料集建構的轉換階段相關聯的參數。
title: 轉換資料集包含檔案
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# 轉換資料集包含檔案{#transformation-dataset-include-files}

{{eol}}

繼承的設定檔的「轉換資料集包含」檔案包含與資料集建構的轉換階段相關聯的參數。

檔案的第一行定義類型 [!DNL TransformationInclude] 支援擴展Dimension、參數、重新處理、階段和轉換參數。 所有其他參數必須定義於 [!DNL Transformation.cfg] 檔案（位於資料集描述檔的資料集目錄中）。

包括擴展Dimension、參數、重新處理、階段和轉換以外的參數， [!DNL Transformation Dataset Include] 檔案會產生錯誤。

您可以為 [!DNL Transformation Dataset Include] 您需要的任何檔案，但其副檔名必須是 [!DNL .cfg]. 檔案必須儲存在 *繼承的設定檔名稱*\Dataset\Transformation目錄。 由於檔案會在資料集建構的轉換階段期間遞回載入，因此您可以儲存 [!DNL Transformation Dataset Include] 在目錄內任何層級的檔案(例如， *繼承的設定檔名稱*\Dataset\Transformation\*資料夾名稱*\*include檔案名稱*.cfg)。

>[!NOTE]
>
>網站的許多Web專屬設定參數定義於 [!DNL Transformation Dataset Include] 檔案。 如需這些參數的相關資訊，請參閱 [Web資料的組態設定](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

下表說明 [!DNL Transformation Dataset Include] 檔案：

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
   <td colname="col2"> 選填。定義延伸維度。 請參閱 <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> 延伸Dimension</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參數 </td> 
   <td colname="col2"> 選填。可在其他設定參數中參照的變數。 如需詳細資訊，請參閱 <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 定義資料集包含檔案中的參數</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新處理 </td> 
   <td colname="col2"> <p>選填。您可以在此處輸入任何字元或字元組合。 變更此參數並儲存檔案會起始資料重新轉換。 </p> <p> 如需重新處理資料的詳細資訊，請參閱 <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新處理和重新轉換</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 階段 </td> 
   <td colname="col2"> <p>選填。套用至此的處理階段名稱 <span class="wintitle"> 轉換資料集包含</span> 檔案。 處理階段在 <span class="filepath"> Transformation.cfg</span> 檔案。 </p> <p> <p>注意：當您指定舞台時，舞台的名稱必須與 <span class="filepath"> Transformation.cfg</span> 檔案。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 轉換 </td> 
   <td colname="col2"> 選填。定義轉換期間需要套用的資料轉換。 如需可用轉換類型的相關資訊，請參閱 <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 資料轉換</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如需 [!DNL Transformation.cfg] 檔案，請參閱 [轉換組態檔](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

使用時，請謹記下列要點 [!DNL Transformation Dataset Include] 檔案：

* 變更此檔案中的任何參數都需要重新轉換資料。
* [!DNL CrossRows], [!DNL ODBCLookup], [!DNL Sessionize]，和 [!DNL AppendURI] 只有在 [!DNL Transformation Dataset Configuration] 檔案。 如需這些轉換的相關資訊，請參閱 [資料轉換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* 您可以將上述任何參數新增至 [!DNL Transformation Dataset Include] 檔案，方法是在記事本中開啟和編輯檔案。 當您在Data Workbench中重新開啟檔案時，您所做和儲存的任何變更都會顯示。 添加新參數時，使用空格鍵（而非Tab鍵）縮進前一個標題級別右側的兩(2)個空格。

如果您訂閱了Adobe [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 資料服務，Adobe提供您內部設定檔，其中包含專為資料服務建立的一組資料轉換和延伸維度。 轉換和維定義於 [!DNL Transformation Dataset Include] 內部設定檔的「資料集」目錄中包含的檔案。 有關安裝 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 資料服務，請參閱 *Data Workbench使用手冊*.
