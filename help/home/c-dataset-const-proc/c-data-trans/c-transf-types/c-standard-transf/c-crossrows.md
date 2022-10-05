---
description: 與其他轉換一樣，CrossRows轉換也會套用至記錄來源中的資料列（記錄項目）。
title: CrossRows
uuid: 5910c150-6bec-4d98-b116-9b382fd54d3c
exl-id: 321f986e-44a9-454c-9311-0ae37a11a088
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 1%

---

# CrossRows{#crossrows}

{{eol}}

與其他轉換一樣，CrossRows轉換也會套用至記錄來源中的資料列（記錄項目）。

對於每一行資料，轉換會取用指定輸入欄位的值，執行一組處理步驟，並將結果記錄在您指定的輸出欄位中。 但若 [!DNL CrossRows] 轉換適用於一列資料（此列稱為輸出列），它會考慮該列加上與相同追蹤ID相關聯的一列或多列其他資料（這些列稱為輸入列）。 因此，對於給定的跟蹤ID，每個輸出行的輸出欄位的值基於一個或多個輸入行的輸入欄位的值。

轉換提供了多個條件和限制，使您能夠限制轉換的輸入行。 您可以透過Data Workbench伺服器的條件來表達這些限制(請參閱 [條件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md))、相對於輸出行的輸入行範圍，或相對於輸出行時間的時間範圍。 對於滿足轉換條件和約束的輸入行，可以應用確定輸出欄位值的操作（如SUM）。

>[!NOTE]
>
>若要運作， [!DNL CrossRows] 轉換需要資料按時間排序，並依來源資料中的追蹤ID分組。 因此， [!DNL CrossRows] 只有在 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案。

查看下表中參數的說明時，請記住以下幾點：

* 輸出行是轉換在給定時間點正在處理的資料行。
* 輸入行是所有其他資料行（在、之後或包括輸出行），其輸入欄位的值用作轉換的輸入。 輸入行受「輸入條件」、「鍵」、「行開始」、「行結束」、「時間開始」和「時間結束」參數的約束。

<table id="table_152851484AFF4C50AF736DC62FAA43E3"> 
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
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 將轉換的輸出限制為某些日誌條目。 如果不符合特定記錄項目的條件，Output參數中的欄位將保持不變。 輸入仍可用於影響其他日誌條目。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 要用作輸入的輸入行的欄位名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入條件 </td> 
   <td colname="col2"> 僅從某些輸入行接受轉換的輸入。 如果特定輸入行的「輸入條件」不滿足，則忽略該行的輸入欄位，而不會影響其他輸出行。 不過，該列的輸出欄位仍會根據指定的條件進行修改。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 金鑰 </td> 
   <td colname="col2"> <p>選填。要作為索引鍵的欄位名稱。 </p> <p> 如果指定了鍵，則給定輸出行的輸入行被限制為與輸出行具有相同鍵值的行的連續塊。 此限制是除了 <span class="wintitle"> CrossRows</span> 轉換。 </p> <p> 例如，如果您使用Web資料，並將欄位x-session-key（每個會話的值都唯一）設為鍵，則轉換的輸入行將限於那些與輸出行具有相同x-session-key值的行。 因此，您僅考慮那些代表頁面檢視的輸入列，這些檢視發生在與輸出列相同的工作階段期間。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>對於每個輸出行，對滿足由「輸入條件」、「鍵」、「行開始」、「行結束」、「時間開始」和「時間結束」參數定義的所有條件的所有輸入行應用一個操作，以生成輸出： 
     <ul id="ul_C01CCF73A9544BCFB7B1105042FEF2DD"> 
      <li id="li_2D1A192970904499AB9F4431D51106D7"> ALL會從輸入行中取用輸入欄位的所有值，並將其輸出為向量。 </li> 
      <li id="li_B8863724AD924DE5BDBC987143548257"> SUM將輸入行中輸入欄位的值解釋為數字並加總。 </li> 
      <li id="li_BF930069DCEA4E0B80893C3C06CAE100"> FIRST ROW從第一輸入行輸出輸入欄位的值。 </li> 
      <li id="li_04B9E2D88C0847E28101FC830C18D8E2"> LAST ROW輸出最後一個輸入行的輸入欄位值。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 輸出欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 行開始/行結束 </td> 
   <td colname="col2"> <p>選填。指定與輸出行相對的輸入行範圍。 例如，「0」的「行開始」值會排除輸出行之前的所有行。 行開始值"1"也排除輸出行。 常見範圍包括： 
     <ul id="ul_B030F32A5146430BA50DD4FAB4A527B0"> 
      <li id="li_30DFB8C0265349C295943A1CB8077B86"> 開始0:此行和所有後續行。 </li> 
      <li id="li_9090C2E94E394351867BC5B78F27B41C"> 開始1:所有後續列。 </li> 
      <li id="li_F870DC913E3F45BA94EE2EC04D344DE0"> 結束0:這行和以前的所有行。 </li> 
      <li id="li_B8A576E419744D84AB1298E5155B583E"> 結束–1:所有先前的列。 </li> 
      <li id="li_CD2307A262D34542A2860FF07005CAD7"> 開始–1，結束–1:上一列。 </li> 
      <li id="li_6BF30B7BB7CC40A68B2332A3C11DD3B5"> 開始1，結束1:下一行。 </li> 
     </ul> </p> </td> 
   <td colname="col3"> 所有列 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始時間/結束時間 </td> 
   <td colname="col2"> <p>選填。指定與輸出行的時間相對的時間範圍。 例如，30分鐘的「時間結束」包含在輸出列後30分鐘內發生的所有列。 -30分鐘的時間開始包含在輸出行之前30分鐘內發生的所有行。 </p> <p> 可用時間單位為天、周、小時、分鐘、毫秒（毫秒）、刻度（100納秒）和ns（納秒）。 </p> </td> 
   <td colname="col3"> 所有時間 </td> 
  </tr> 
 </tbody> 
</table>

此 [!DNL CrossRows] 此範例中的轉換會套用至網頁資料列，以尋找每個頁面檢視的下一個頁面檢視時間。 因為我們知道 [!DNL CrossRows] 只有在資料集建構程式的轉換階段才會套用，資料列會依訪客（每位訪客都有不重複的追蹤ID）和時間排序。

輸入欄位x-timestamp僅會針對填入了x-is-page-view欄位的輸入列（表示資料列代表頁面檢視）而考慮。 會為Key參數指定x-session-key欄位（每個工作階段的值都有唯一值）。 因此，用於轉換的輸入行（日誌條目）被限制為與輸出行具有相同x-session-key值的連續行塊。 換言之，要考慮轉換，輸入行必須代表在與輸出行中的頁面檢視相同的工作階段期間發生的頁面檢視。 第一行操作從滿足以下條件的第一輸入行取出輸出欄位的值 [!DNL Input] 條件，且與輸出列具有相同的x-session-key值。

![](assets/cfg_TransformationType_CrossRows.png)

[!DNL CrossRows] 以與其輸入大小加上其輸出大小成比例的時間量執行。 這表示對於操作SUM 、 FIRST ROW和LAST ROW ，它的效率與其他轉換一樣低。 對於ALL，情況更複雜，因為可以進行配置 [!DNL CrossRows] 輸出與指定追蹤ID的總列數（記錄項目）成比例的每列資料量（記錄項目）。
