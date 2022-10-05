---
description: 若您使用的是網站資料，則可使用ExtractValue轉換，從網站資料中的查詢字串、Cookie或類似編碼欄位擷取值。
title: ExtractValue
uuid: 305827a2-04e6-421f-82cb-923d62b02e70
exl-id: 5bafe64f-081a-49ec-997e-68e8f6915a71
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# ExtractValue{#extractvalue}

{{eol}}

若您使用的是網站資料，則可使用ExtractValue轉換，從網站資料中的查詢字串、Cookie或類似編碼欄位擷取值。

請注意，與要擷取的值對應的名稱在每個記錄項目中可能不同。

<table id="table_D16A39BE035043628A4D6F7452952304"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 套用此轉換的條件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入名稱 </td> 
   <td colname="col2"> <p>要從輸入查詢中提取的欄位名稱。 </p> <p> <p>注意：如果「輸入名稱」是向量（即存在多個名稱），則只會擷取一個值。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入查詢 </td> 
   <td colname="col2"> 要擷取值的編碼對應（查詢字串、Cookie等）。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出值 </td> 
   <td colname="col2"> 用於捕獲提取的解碼值的欄位的名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

如果您想要擷取搜尋詞，可以擷取整個片語，並視需要使用 [!DNL Tokenize] 轉換。 如需 [!DNL Tokenize] 轉換，請參閱 [Tokenize](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-tokenize.md#concept-f460aa5df3a7476e971af29cf5d9b32c).

此範例會設定 [!DNL ExtractValue] 轉換，從cs(referrer-query)擷取x-v-search-querynames欄位的值，並將其儲存在x-search-phrase欄位中。

![](assets/cfg_TransformationType_ExtractValue.png)
