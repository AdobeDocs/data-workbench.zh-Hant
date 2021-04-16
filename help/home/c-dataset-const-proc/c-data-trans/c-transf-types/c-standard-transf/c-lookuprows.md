---
description: LookupRows轉換會查看具有相同追蹤ID的其他記錄項目，並將輸出欄位的值設定為輸入列中指定欄位的值。
title: LookupRows
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
exl-id: caa9a311-b056-4fe8-bb11-1605cc690375
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 0%

---

# LookupRows{#lookuprows}

LookupRows轉換會查看具有相同追蹤ID的其他記錄項目，並將輸出欄位的值設定為輸入列中指定欄位的值。

由於[!DNL LookupRows]轉換會對日誌條目執行查找，而不是查找檔案，因此與[!DNL CrossRows]轉換非常相似。 請參閱[CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)。

要運作，[!DNL LookupRows]轉換要求資料按時間排序，並依來源資料中的追蹤ID分組。 因此，[!DNL LookupRows]僅在[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中定義時運作。

在查看下表中參數的說明時，請記住以下內容：

* 輸出行是轉換在給定時間點處理的資料行。
* 輸入行是所有其它資料行（在輸出行之前、之後或包括輸出行），其輸入欄位的值用作轉換的輸入。

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 將轉換的輸出限制為某些日誌條目。 如果某個特定日誌條目不符合該條件，則「輸出行值輸出」參數中的欄位保持不變。 該輸入仍可用於影響其他日誌條目。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入條件 </td> 
   <td colname="col2">僅接受特定輸入行的轉換輸入。 如果特定輸入行的<span class="wintitle">輸入</span>條件不滿足，則忽略該行的輸入欄位，並不影響其他輸出行。 不過，該行的輸出欄位仍會根據指定的條件進行修改。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入行鍵輸入 </td> 
   <td colname="col2"> 要用作輸入行鍵的欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入行值輸入 </td> 
   <td colname="col2"> 如果滿足所有條件，則輸入行中欄位的名稱，其值將被複製到「輸出行值輸出」參數中的欄位。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>對於每個輸出行，對滿足<span class="wintitle">輸入</span>條件和輸入行鍵輸入參數定義的所有條件的所有輸入行應用該操作以生成輸出： 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST從資料中第一個匹配輸入行（而不是輸出行後的第一個匹配行）輸出「輸入行值輸入」參數中欄位的值。 </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST從資料的最後一個輸入行（而不是輸出行之前的最後一個匹配行）輸出「輸入行值輸入」參數中欄位的值。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出行鍵輸入 </td> 
   <td colname="col2"> 要用作輸出行鍵的欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出行值輸出 </td> 
   <td colname="col2">如果滿足所有條件，則輸出行中欄位的名稱，其值將從「輸入行值輸入」參數中的欄位中複製。 所有具有相同x-trackingid和<span class="wintitle">輸出行鍵輸入</span>值的輸出行都具有相同的<span class="wintitle">輸出行值輸出</span>值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

輸入行鍵輸入、輸入行值輸入和輸入條件參數一起定義每個跟蹤ID的查找檔案，而輸出行鍵輸入、輸出行值輸入和條件參數控制檔案中查找的內容和儲存在輸出行值輸出指定欄位中的值。

要更好地瞭解轉換的操作，請考慮以下大綱：

* 對於滿足條件且具有非空輸出行鍵輸入的每個輸出行：

   * 尋找FIRST或LAST輸入列，如此

      * 輸入行滿足輸入條件，並且
      * 輸入列的x-trackingid等於輸出列的x-trackingid，以及
      * 輸入行的輸入行鍵輸入等於輸出行的輸出行鍵輸入。

* 並將輸出行的輸出行值輸出設定為輸入行的輸入行值輸入。

[!DNL LookupRows]的注意事項

* 空白的索引鍵值永遠不符合任何項目。 即使輸入行中有空白鍵和非空白值與[!DNL Input Condition]匹配，「」的[!DNL Output Row Key Input]也始終會生成「」的[!DNL Output Row Value Output]。

* 如果[!DNL Input Condition]未禁止，則行的[!DNL Input Row Key Input]和[!DNL Output Row Key Input]值相同時，行可能會自查。

如果您有多個鍵值，則可在套用[!DNL LookupRows]轉換前，使用[!DNL Format]轉換（請參閱[格式](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)）來組合這些鍵值。

假設您有一個網站，其中有寵物註冊頁面，輸入了寵物的名稱和品種，以及一個稍後的「購買玩具」頁面，其中只使用寵物的名稱。 您希望能夠將寵物名稱與在註冊頁面上輸入的寵物品種連結起來。 若要這麼做，您可以建立下列[!DNL LookupRows]轉換：

![](assets/cfg_TransformationType_LookupRows.png)

讓我們使用上一個大綱來分析此示例：

* 對於滿足cs-uri-query(petname)非空值的每個輸出行：

   * 查找LAST輸入行，以便

      * 輸入行包含cs-uri-query(petbreed)的非空值，且
      * 輸入列的x-trackingid等於輸出列的x-trackingid，以及
      * 輸入行的cs-uri-query(petname)值等於輸出行的cs-uri-query(petname)值，

* 並將輸出行的x-pet-breed值設定為輸入行的cs-uri-query(petbreed)值。

[!DNL LookupRows]轉換使用寵物名稱（密鑰）來確保寵物品種與寵物註冊和購買玩具頁面都相連結，以便您分析每種寵物所購買的玩具，即使是對有多隻寵物的訪客。
