---
description: 繼承配置檔案的日誌處理資料集包含檔案包含與資料集構建的日誌處理階段相關聯的參數。
solution: Analytics
title: 記錄處理資料集包含檔案
topic: Data workbench
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 記錄處理資料集包含檔案{#log-processing-dataset-include-files}

繼承配置檔案的日誌處理資料集包含檔案包含與資料集構建的日誌處理階段相關聯的參數。

檔案的第一行定 [!DNL Log Processing Dataset Include] 義了支援「解碼器 [!DNL LogProcessingInclude] 群組」、「欄位」、「記錄項目條件」、「參數」、「重新處理」、「舞台」和「轉換」參數的類型。 記錄處理的所有其他參數必須在資料集描述檔 [!DNL Log Processing.cfg] 的資料集目錄的檔案中定義。 您可以為檔案 [!DNL Log Processing Dataset Include] 命名任何項目，但其副檔名必須為 [!DNL .cfg]。 檔案必須儲存在繼承的描述檔名 *稱\Dataset\Log Processing directory中*。 由於檔案是在資料集建構的記錄處理階段以遞歸方式載入，因此您可以將檔案儲存在目錄中的任何層級(例如，繼承的描述檔名稱 [!DNL Log Processing Dataset Include]**\Dataset\Log Processing\*檔案夾名稱*\*include file name*.cfg)。

>[!NOTE]
>
>許多網站的特定Web組態參數都在檔案中 [!DNL Log Processing Dataset Include] 定義。 如需這些參數的詳細資訊，請參 [閱Web資料的組態設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

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
   <td colname="col2"> <p>如果您已在「記錄處理。cfg」檔案中定義記錄檔或XML檔案記錄 <span class="filepath"> 來源，則此為必要項</span> 。 您定義的文字檔或XML解碼器，可從記錄檔和XML記錄檔來源擷取資料欄位。 </p> <p> <b>若要新增解碼器群組</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> 在「解碼器群組 <span class="uicontrol"> 」上按一下滑鼠右鍵</span> ，然後按一下「新增 <span class="uicontrol"> &gt;</span> TextFileDecoderGroup」或 <span class="uicontrol"></span><span class="uicontrol"></span>XMLDecoderGroup。 </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> 在新群組的「名稱」參數中，輸入所要的解碼器群組名稱。 </li> 
     </ul> </p> <p> <p>注意： 當您在資料集描述檔的 <span class="filepath"></span> Log Processing.cfg檔案中指定解碼器群組時，名稱必須與您在此處輸入的名稱完全相符。 如需詳細資訊，請參 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> 閱記錄檔</a>。 </p> </p> <p> 如需您可以為每個群組定義之解碼器的詳細資訊，請參閱「文字檔 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> 解碼器群組</a> 」 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> 或「XML解碼器群組」</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 欄位 </td> 
   <td colname="col2"> <p>列出在「日誌處理資料集配置 <span class="wintitle"> 」檔案的「日誌源</span> 」或「轉換」中定義，但在「轉換資料集配置檔案」的轉換、條件、擴展維中使用的欄位， <span class="wintitle"></span><span class="wintitle"></span><span class="wintitle"></span> 此處必須列出這些欄位。 </p> <p> 下列每個欄位必須列在某些記錄處理資 <span class="wintitle"> 料集包含檔案中</span> : 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌條目條件 </td> 
   <td colname="col2"> <p>選填。定義將日誌條目納入資料集的規則。 請參 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 閱記錄項目條件</a>。 </p> <p> <p>注意： 若要包含在資料集中，記錄項目必須符合 <span class="wintitle"> Log Processing.cfg檔案和每個</span> Log Processing Dataset Include檔案中的「記錄項目條件 <span class="filepath"> 」(Log Entry Condition</span><span class="wintitle"></span> )。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參數 </td> 
   <td colname="col2"> 選填。可在其他配置參數中引用的變數。 如需詳細資訊，請參 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 閱「在資料集中定義參數包含檔案」</a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重新處理 </td> 
   <td colname="col2"> <p>選填。您可在此處輸入任何字元或字元組合。 變更此參數並將檔案儲存至資料工作台伺服器後，會開始資料重新處理。 </p> <p> 如需重新處理資料的詳細資訊，請參閱重新 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 處理和重新轉換</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>選填。套用至此記錄處理資料集包含檔案 <span class="wintitle"> 的處理階段名稱</span> 。 處理階段是在Log Processing.cfg檔案的「階段 <span class="filepath"> 」參數中定義</span> 。 </p> <p> <p>注意： 當您指定舞台時，舞台的名稱必須與資料集描述檔的 <span class="filepath"></span> Log Processing.cfg檔案中Stages參數中所列的名稱完全相符。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 轉換 </td> 
   <td colname="col2"> 選填。定義在日誌處理過程中需要應用的資料轉換。 有關可用轉換類型的資訊，請參 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 閱資料轉換</a>。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>有關檔案中參數的說明，請 [!DNL Log Processing.cfg] 參閱日 [志處理配置檔案](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。

當您使用檔案時，應牢記下列 [!DNL Log Processing Dataset Include] 點：

* 若要變更此檔案中的任何參數，必須重新處理所有資料。
* 通過在記事本中開啟和編輯檔案，可 [!DNL Log Processing Dataset Include] 以將上述任何參數添加到檔案中。 當您在資料工作台中重新開啟檔案時，您所做的任何變更和儲存都會出現。 添加新參數時，請使用空格鍵（而非Tab鍵）在前一個標題級別的右側縮進兩(2)個空格。

