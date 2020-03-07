---
description: LookupRows轉換會查看具有相同追蹤ID的其他記錄項目，並將輸出欄位的值設定為輸入列中指定欄位的值。
solution: Analytics
title: LookupRows
topic: Data workbench
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# LookupRows{#lookuprows}

LookupRows轉換會查看具有相同追蹤ID的其他記錄項目，並將輸出欄位的值設定為輸入列中指定欄位的值。

由於轉 [!DNL LookupRows] 換會對日誌條目執行查找，而不是查找檔案，因此它與轉換非常 [!DNL CrossRows] 相似。 請參 [閱CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)。

若要運作，轉 [!DNL LookupRows] 換需要資料按時間排序，並依來源資料中的追蹤ID分組。 因此， [!DNL LookupRows] 只有在檔案或檔案中 [!DNL Transformation.cfg] 定義時才可 [!DNL Transformation Dataset Include] 用。

在查看下表中參數的說明時，請記住以下內容：

* 輸出行是轉換在給定時間點處理的資料行。
* 輸入行是所有其它資料行（在輸出行之前、之後或包括輸出行），其輸入欄位的值用作轉換的輸入。

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
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
   <td colname="col2">僅接受特定輸入行的轉換輸入。 如果特 <span class="wintitle"> 定輸入行不滿足「輸入條件</span> 」，則忽略該行的輸入欄位，而不會影響其他輸出行。 不過，該行的輸出欄位仍會根據指定的條件進行修改。 </td> 
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
   <td colname="col2"> <p>對於每個輸出行，對滿足「輸入條件」和「輸入行鍵輸入」參數定義的所有條件的所有輸入行應用一個操作，以生成輸出： <span class="wintitle"></span> 
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
   <td colname="col2">如果滿足所有條件，則輸出行中欄位的名稱，其值將從「輸入行值輸入」參數中的欄位中複製。 具有相同x-trackingid和輸出行鍵輸入值的所 <span class="wintitle"> 有輸出行 </span>都具有相同 <span class="wintitle"> 的輸出行值輸出值</span> 。 </td> 
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

注意事項 [!DNL LookupRows]

* 空白的索引鍵值永遠不符合任何項目。 即使輸入行中有空白鍵和非空白值與匹配 [!DNL Input Condition], [!DNL Output Row Key Input] &quot;&quot;也一律會產生 [!DNL Output Row Value Output] &quot;&quot;。

* 如果行和值 [!DNL Input Condition]相同，則行不被禁 [!DNL Input Row Key Input] 止 [!DNL Output Row Key Input] ，可能會自查。

如果您有多個索引鍵值，則可在套用轉換前，使 [!DNL Format] 用轉換(請參 [閱格式](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b))來合併 [!DNL LookupRows] 這些值。

假設您有一個網站，其中有寵物註冊頁面，輸入了寵物的名稱和品種，以及一個稍後的「購買玩具」頁面，其中只使用寵物的名稱。 您希望能夠將寵物名稱與在註冊頁面上輸入的寵物品種連結起來。 若要這麼做，您可以建立下列轉 [!DNL LookupRows] 換：

![](assets/cfg_TransformationType_LookupRows.png)

讓我們使用上一個大綱來分析此示例：

* 對於滿足cs-uri-query(petname)非空值的每個輸出行：

   * 查找LAST輸入行，以便

      * 輸入行包含cs-uri-query(petbreed)的非空值，且
      * 輸入列的x-trackingid等於輸出列的x-trackingid，以及
      * 輸入行的cs-uri-query(petname)值等於輸出行的cs-uri-query(petname)值，

* 並將輸出行的x-pet-breed值設定為輸入行的cs-uri-query(petbreed)值。

這 [!DNL LookupRows] 項轉換使用寵物名稱（密鑰）來確保寵物品種與寵物註冊和購買玩具頁面都相關聯，這樣，你就可以分析每種寵物所購買的玩具，即使是有多隻寵物的遊客。
