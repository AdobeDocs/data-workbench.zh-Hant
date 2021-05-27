---
description: 格式轉換採用一組輸入，並對其進行格式化，以建立與給定結構匹配的輸出。
title: 格式
uuid: c596902e-21bc-4ce6-9ca4-7ca86dfc0a6c
exl-id: 842b502e-cd16-45b3-ada8-6f2d899f1d54
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 3%

---

# 格式{#format}

格式轉換採用一組輸入，並對其進行格式化，以建立與給定結構匹配的輸出。

該轉換對簡單字串或字串向量起作用，並通過將給定格式應用於每個輸入值來產生輸出，直到所有輸入值都經過轉換。

<table id="table_3953C993167248AA9A47964A51C4AB5D"> 
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
   <td colname="col1"> 格式 </td> 
   <td colname="col2"> <p>用於指定輸出外觀的格式字串。 </p> <p> %1%引用來自第一輸入向量的值，%2%引用來自第二輸入向量的值，以此類推。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <p>包含簡單字串或字串向量的欄位。 在字串向量作為輸入的情況下，輸出也將是字串向量，該字串向量由將<span class="wintitle"> Format</span>參數應用於每組輸入值而產生。 </p> <p> <p>注意： 輸入的編號從0開始，但格式替代值的編號從%1%開始。 </p> </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 為包含轉換結果而建立的欄位的名稱。 如果輸入為字串向量，則輸出字串向量的長度將是最長輸入向量的長度。 如果某些輸入字串向量長度較短，則在達到輸出向量長度之前，在格式字串中用於其位置的空字串。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

在此範例中，兩個向量（一個代表產品類別的字串向量，另一個代表每個購買產品數量的對應字串向量）轉換為具有等同長度的單一向量，其形式如下：產品%1%，數量%2%。

![](assets/cfg_TransformationType_Format.png)

如果輸入向量包含(683,918)的產品類別和(10,4)的數量，則結果將是包含以下兩個字串的一個最終輸出向量：（「產品683，數量10」、「產品918，數量4」）。
