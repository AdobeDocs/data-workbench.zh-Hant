---
description: RETransform（規則運算式）轉換是一種模式匹配轉換，它使用規則運算式指定模式以在輸入中查找和捕獲，並將捕獲的字串儲存在指定的輸出欄位中。
title: RETransform
uuid: 60b5b60e-678a-416d-b5c3-57b1bbefce7d
exl-id: 2595f782-0efb-4a2a-84bd-fdb04baf0852
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 3%

---

# RETransform{#retransform}

RETransform（規則運算式）轉換是一種模式匹配轉換，它使用規則運算式指定模式以在輸入中查找和捕獲，並將捕獲的字串儲存在指定的輸出欄位中。

規則運算式會根據整個輸入字串進行計算。 如果輸入與規則運算式中指定的模式不符，則不會擷取任何資料。 有關使用規則運算式的簡要指南，請參見[規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)。

>[!NOTE]
>
>[!DNL RETransform]轉換的運作類似於[!DNL REMatch]轉換（請參見[REMatch](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-rematch.md#concept-7f0b1caad1df46aabef4448f88261a8e)），它為規則運算式中的每個捕獲子模式構建一個輸出欄位。 您可以將[!DNL RETransform]看作[!DNL REMatch]和[!DNL Format]轉換的組合。 如果Action參數（請參閱下表中的Action）設為&quot;RESULTS&quot;，則[!DNL RETransform]的運作方式就像[!DNL REMatch]和[!DNL Union]轉換的組合。

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
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設 </td> 
   <td colname="col2"> 如果條件符合且輸入值不可用或規則運算式不符合輸入值，則使用的預設值。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 動作 </td> 
   <td colname="col2"> <p>指定結果的處理方式。 RESULTS的預設設定只會採用匹配的模式，並從所提取的模式建立字串向量。 </p> <p> 或者，該動作可以是用於建立特定格式的簡單字串輸出的格式字串。 使用此技術，您可以指定與每個匹配模式在%符號之間的位置對應的數字。 例如，第1個相符模式為%1%，第3個相符模式為%3%。 您可以字面地在格式字串中指定其他字元。 </p> </td> 
   <td colname="col3"> 結果 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 運算式 </td> 
   <td colname="col2"> 用於匹配的規則運算式。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 計算規則運算式的欄位。 </td> 
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
>[!DNL RETransform] 轉換可能非常緩慢，而且可能佔據大部分資料處理時間。

此範例會隔離網站訪客所使用的Windows作業系統版本，並建立欄位x-windows版本與該值。 在此例中，輸出值只是版本號。

![](assets/cfg_TransformationType_RegularExpression.png)

如果您想在版本號碼前面加入&quot;Version&quot;字串，以方便閱讀，您可將Action參數從&quot;RESULTS&quot;變更為&quot;Version %1%&quot;。 若要在輸出中加入常值百分號(%)，請使用第二個百分號逸出，如同在「%」中。
