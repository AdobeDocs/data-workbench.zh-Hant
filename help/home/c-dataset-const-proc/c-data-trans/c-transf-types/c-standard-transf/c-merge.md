---
description: 合併轉換會從輸入欄位（通常是字串的向量）取用值，將它們合併為由指定分隔字元分隔的單一字串，並將產生的字串放入指定的輸出欄位中。
title: Merge
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
exl-id: 75fa824b-f68d-4ec4-a75d-0f742a7bb1ba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 5%

---

# 合併{#merge}

{{eol}}

合併轉換會從輸入欄位（通常是字串的向量）取用值，將它們合併為由指定分隔字元分隔的單一字串，並將產生的字串放入指定的輸出欄位中。

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
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
   <td colname="col2"> 在符合條件且輸入值不可用時使用的預設值。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用於在單個輸出字串中分隔輸入字串向量的各個元素的字串。 </p> <p> 按住Ctrl鍵並在「分隔字元」參數內按一下滑鼠右鍵， <span class="wintitle"> 插入</span> 中。 此菜單包含通常用作分隔符的特殊字元的清單。 </p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 組合以形成輸出字串的字串值的向量。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 輸出字串的名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

在此範例中，假設字串的輸入向量包含一組已選取要購買的產品。 這些產品會放入單一輸出字串中，並以「：：」（兩個冒號）分隔。

![](assets/cfg_TransformationType_Merge.png)

因此，如果輸入欄位x-products包含字串值B57481、C46355和Z97123，則產生的輸出字串x-show-products將是B57481::C46355::Z97123。
