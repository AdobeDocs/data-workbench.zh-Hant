---
description: 繼承的設定檔的「記錄處理資料集包含」檔案包含與資料集建構的記錄處理階段相關聯的參數。
title: 記錄處理資料集包含檔案
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# 記錄處理資料集包含檔案{#log-processing-dataset-include-files}

{{eol}}

繼承的設定檔的「記錄處理資料集包含」檔案包含與資料集建構的記錄處理階段相關聯的參數。

第一行 [!DNL Log Processing Dataset Include] 檔案定義類型 [!DNL LogProcessingInclude] 支援解碼器群組、欄位、記錄項目條件、參數、重新處理、階段和轉換參數。 記錄處理的所有其他參數必須定義於 [!DNL Log Processing.cfg] 檔案（位於資料集描述檔的資料集目錄中）。 您可以為 [!DNL Log Processing Dataset Include] 您需要的任何檔案，但其副檔名必須是 [!DNL .cfg]. 檔案必須儲存在 *繼承的設定檔名稱*\資料集\日誌處理目錄。 由於檔案會在資料集建構的記錄處理階段期間遞回載入，因此您可以儲存 [!DNL Log Processing Dataset Include] 在目錄內任何層級的檔案(例如， *繼承的設定檔名稱*\Dataset\Log Processing\*資料夾名稱*\*包含檔案名稱*.cfg)。

>[!NOTE]
>
>網站的許多Web專屬設定參數定義於 [!DNL Log Processing Dataset Include] 檔案。 如需這些參數的相關資訊，請參閱 [Web資料的組態設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 解碼器群組 </td> 
   <td colname="col2"> <p>如果您已在 <span class="filepath"> Log Processing.cfg</span> 檔案。 定義的文本檔案或XML解碼器，用於從日誌檔案和XML日誌源中提取資料欄位。 </p> <p> <b>新增解碼器群組的方式</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> 按一下右鍵 <span class="uicontrol"> 解碼器群組</span> 按一下 <span class="uicontrol"> 新增</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> 或 <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> 在新群組的「名稱」參數中，輸入解碼器群組的所需名稱。 </li> 
     </ul> </p> <p> <p>注意：當您在 <span class="filepath"> Log Processing.cfg</span> 資料集設定檔的檔案，名稱必須與您在此輸入的名稱完全相符。 如需詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> 記錄檔</a>. </p> </p> <p> 如需可為每個群組定義之解碼器的相關資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> 文字檔案解碼器群組</a> 或 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML解碼器群組</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 欄位 </td> 
   <td colname="col2"> <p>列出中定義的欄位 <span class="wintitle"> 記錄來源</span> 或 <span class="wintitle"> 轉換</span> 在 <span class="wintitle"> 記錄處理資料集組態</span> 檔案，但用於 <span class="wintitle"> 轉換資料集組態</span> 檔案必須列於此處。 </p> <p> 以下每個欄位必須列在 <span class="wintitle"> 記錄處理資料集包含</span> 檔案： 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 記錄項目條件 </td> 
   <td colname="col2"> <p>選填。定義將記錄項目納入資料集的規則。 請參閱 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 記錄項目條件</a>. </p> <p> <p>注意：若要納入資料集，記錄項目必須符合 <span class="wintitle"> 記錄項目條件</span> 在 <span class="filepath"> Log Processing.cfg</span> 檔案和 <span class="wintitle"> 記錄處理資料集包含</span> 檔案。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參數 </td> 
   <td colname="col2"> 選填。可在其他設定參數中參照的變數。 如需詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 定義資料集包含檔案中的參數</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新處理 </td> 
   <td colname="col2"> <p>選填。您可以在此處輸入任何字元或字元組合。 變更此參數並將檔案儲存至Data Workbench伺服器時，會起始資料重新處理。 </p> <p> 如需重新處理資料的詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新處理和重新轉換</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 階段 </td> 
   <td colname="col2"> <p>選填。套用至此的處理階段名稱 <span class="wintitle"> 記錄處理資料集包含</span> 檔案。 處理階段在 <span class="filepath"> Log Processing.cfg</span> 檔案。 </p> <p> <p>注意：當您指定舞台時，舞台的名稱必須與 <span class="filepath"> Log Processing.cfg</span> 檔案。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 轉換 </td> 
   <td colname="col2"> 選填。定義記錄處理期間需要套用的資料轉換。 如需可用轉換類型的相關資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 資料轉換</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如需 [!DNL Log Processing.cfg] 檔案，請參閱 [記錄處理組態檔](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

使用時，請謹記下列要點 [!DNL Log Processing Dataset Include] 檔案：

* 若要變更此檔案中的任何參數，必須重新處理所有資料。
* 您可以將上述任何參數新增至 [!DNL Log Processing Dataset Include] 檔案，方法是在記事本中開啟和編輯檔案。 當您在Data Workbench中重新開啟檔案時，您所做和儲存的任何變更都會顯示。 添加新參數時，使用空格鍵（而非Tab鍵）縮進前一個標題級別右側的兩(2)個空格。
