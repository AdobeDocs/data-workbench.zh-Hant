---
description: 如果您使用Web資料，可使用ExtractValue轉換從網站資料的查詢字串、Cookie或類似編碼欄位擷取值。
solution: Analytics
title: ExtractValue
topic: Data workbench
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ExtractValue{#extractvalue}

如果您使用Web資料，可使用ExtractValue轉換從網站資料的查詢字串、Cookie或類似編碼欄位擷取值。

請注意，與要提取的值對應的名稱在每個日誌條目中可能不同。

<table id="table_D16A39BE035043628A4D6F7452952304"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入名稱 </td> 
   <td colname="col2"> <p>要從「輸入查詢」中提取的欄位的名稱。 </p> <p> <p>注意： 如果「輸入名稱」是向量（即存在多個名稱），則只提取一個值。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入查詢 </td> 
   <td colname="col2"> 要從中擷取值的編碼對應（查詢字串、Cookie等）。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出值 </td> 
   <td colname="col2"> 用於擷取擷取解碼值的欄位名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

如果您想擷取搜尋片語，可以擷取整個片語，並視需要使用轉換將片語分割為搜尋 [!DNL Tokenize] 詞。 有關轉換的信 [!DNL Tokenize] 息，請參 [閱Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c)。

此範例會設 [!DNL ExtractValue] 定轉換，從cs(referrer-query)擷取x-v-search-querynames欄位的值，並將它們儲存在x-search-phrase欄位中。

![](assets/cfg_TransformationType_ExtractValue.png)

