---
description: RETransform（規則運算式）轉換是一種模式匹配轉換，它使用規則運算式指定要在輸入中查找和捕獲的模式，並將捕獲的字串儲存在指定的輸出欄位中。
title: RETransform
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
exl-id: 2595f782-0efb-4a2a-84bd-fdb04baf0852
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 3%

---

# RETransform{#retransform}

RETransform（規則運算式）轉換是一種模式匹配轉換，它使用規則運算式指定要在輸入中查找和捕獲的模式，並將捕獲的字串儲存在指定的輸出欄位中。

對整個輸入字串計算規則運算式。 如果輸入與規則運算式中指定的模式不符，則不會擷取任何資料。 如需使用規則運算式的簡短指南，請參閱[規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)。

>[!NOTE]
>
>[!DNL RETransform]轉換的操作與[!DNL REMatch]轉換類似（請參見[REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)），它為規則表達式中的每個捕獲子模式構建一個輸出欄位。 您可以將[!DNL RETransform]想像為[!DNL REMatch]和[!DNL Format]轉換的組合。 如果Action參數（請參閱下表中的Action）設定為&quot;RESULTS&quot;，則[!DNL RETransform]的操作方式與[!DNL REMatch]和[!DNL Union]轉換的組合相同。

<table id="table_51B7342E6A5E4E31913BD0F6A6ACC424"> 
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
   <td colname="col1"> 預設 </td> 
   <td colname="col2"> 在符合條件且輸入值不可用或規則運算式不符合輸入值時，要使用的預設值。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 動作 </td> 
   <td colname="col2"> <p>指定結果的處理方式。 預設的RESULTS設定只需獲取匹配的模式，並從所提取的模式中建立字串向量。 </p> <p> 或者，該動作可以是格式字串，以建立特定格式的簡單字串輸出。 使用此技術，您可以指定與%符號之間每個匹配模式的位置對應的數字。 例如，第1個匹配模式為%1%，第3個匹配模式為%3%。 您可以字面地在格式字串中指定其他字元。 </p> </td> 
   <td colname="col3"> 結果 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 運算式 </td> 
   <td colname="col2"> 用於比對的規則運算式。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 用於計算規則運算式的欄位。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 輸出字串的名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL RETransform] 轉換可能會非常緩慢，而且可能會佔據資料處理時間的很大一部分。

此範例會隔離網站訪客所使用的Windows作業系統版本，並從該值建立欄位x-windows-version。 在此情況下，輸出值將只是版本號。

![](assets/cfg_TransformationType_RegularExpression.png)

如果要在版本號前面包含字串&quot;Version&quot;，以便閱讀，則會將Action參數從&quot;RESULTS&quot;更改為&quot;Version %1%&quot;。 若要在輸出中加入文字百分比符號(%)，請以第二個百分比符號逸出，如「%%」。
