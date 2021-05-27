---
description: REMatch轉換是一種模式匹配轉換，它使用規則表達式指定要在輸入中查找和捕獲的一個或多個模式。
title: REMatch
uuid: 8ef80bfa-aea2-45a1-a7d9-38ad33043886
exl-id: 571e6f1c-f557-49c3-9e7c-c31f06132ec7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 4%

---

# REMatch{#rematch}

REMatch轉換是一種模式匹配轉換，它使用規則表達式指定要在輸入中查找和捕獲的一個或多個模式。

該轉換為規則運算式中每個擷取子模式建構一輸出欄位。 如果規則運算式與輸入欄位不匹配，則輸出為空，如果輸出欄位已存在，則值將替換為空白值。 如需使用規則運算式的簡短指南，請參閱[規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)。

>[!NOTE]
>
>[!DNL REMatch]轉換的運作方式與[!DNL RETransform]轉換類似（請參閱[RETransform](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-retransform.md#concept-23f80aa0bc204565b337e5c4931f6a74)），該轉換使用規則運算式來擷取字串，並將該字串儲存在單一輸出欄位中。

[!DNL REMatch] 比多個轉換或單個轉 [!DNL RETransform] 換及後續的轉 [!DNL RETransform] 換更有效率地分 [!DNL Flatten] 析字串。請參閱[Flatten](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-flatten.md#concept-7acd351a6d2444bd960ca412ae3333ce)。

<table id="table_7077578512B249E986BC79AE770CBD9A"> 
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
   <td colname="col1"> 區分大小寫 </td> 
   <td colname="col2"> True 或 False. 指定匹配是否區分大小寫。 </td> 
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
   <td colname="col2"> <p>輸出字串或向量的名稱。 在字串向量作為輸入的情況下，輸出也是字串向量。 </p> <p> 運算式中每個擷取子模式都必須存在輸出欄位。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>[!DNL REMatch] 轉換可能會非常緩慢，而且可能會佔據資料處理時間的很大一部分。

在此範例中，[!DNL REMatch]轉換會將YYYY-MM-DD格式的日期剖析為x年、x月和x日欄位。 對於2007-01-02日期，x年、x月和x日的值將分別為2007、01和02。

![](assets/cfg_TransformationType_REMatch.png)
