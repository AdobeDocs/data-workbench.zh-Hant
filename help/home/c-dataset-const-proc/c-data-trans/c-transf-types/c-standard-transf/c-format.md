---
description: 「格式」(Format)轉換會使用一組輸入並格式化它們，以建立與給定結構匹配的輸出。
solution: Analytics
title: 格式
topic: Data workbench
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 格式{#format}

「格式」(Format)轉換會使用一組輸入並格式化它們，以建立與給定結構匹配的輸出。

轉換適用於簡單字串或字串向量，並通過將給定格式應用於每個輸入值直到所有輸入值都轉換完畢而生成輸出。

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col1"> 格式 </td> 
   <td colname="col2"> <p>用於指定輸出外觀的格式字串。 </p> <p> %1%是指來自第一個輸入向量的值，%2%指來自第二個輸入向量的值，依此類推。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <p>包含簡單字串或字串向量的欄位。 如果字串向量是輸入，則輸出也是由將 <span class="wintitle"></span> Format參數應用到每組輸入值所產生的字串向量。 </p> <p> <p>注意： 輸入的編號從0開始，但格式替代值的編號從%1%開始。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 為包含轉換結果而建立的欄位的名稱。 如果輸入為字串向量，則輸出字串向量的長度將是最長輸入向量的長度。 如果某些輸入字串向量的長度較短，則空字串用於它們在格式字串中的位置，直到達到輸出向量的長度。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

在此範例中，兩個向量（一個代表產品類別的字串向量，另一個代表每個購買產品的數量的對應字串向量）會轉換為具有下列格式的等效長度的單一向量：產品%1%，數量%2%。

![](assets/cfg_TransformationType_Format.png)

如果輸入向量包含(683, 918)的乘積類別和(10, 4)的數量，則結果將是包含下列兩個字串的最終輸出向量：（「產品683，數量10」、「產品918，數量4」）。
