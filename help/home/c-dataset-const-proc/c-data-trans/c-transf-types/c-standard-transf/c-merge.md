---
description: 「合併」轉換會從輸入欄位（通常是字串的向量）取值，將這些值合併為由指定分隔字元分隔的單一字串，並將產生的字串放入指定的輸出欄位。
solution: Analytics
title: 合併
topic: Data workbench
uuid: 9ca2ab22-d854-47b0-8189-f563c1e83d1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 合併{#merge}

「合併」轉換會從輸入欄位（通常是字串的向量）取值，將這些值合併為由指定分隔字元分隔的單一字串，並將產生的字串放入指定的輸出欄位。

<table id="table_2458E008C9A14B31A774E6819D07E9BE"> 
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
   <td colname="col1"> 預設值 </td> 
   <td colname="col2"> 如果條件符合且輸入值不可用，則使用的預設值。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用來分隔單一輸出字串中輸入字串向量的個別元素的字串。 </p> <p> 如果按住Ctrl鍵並在分隔字元參數內按一下滑鼠右鍵，則會出現「插入 <span class="wintitle"> 」功能表</span> 。 此功能表包含常用作分隔字元的特殊字元清單。 </p> </td> 
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

在此範例中，假設字串的輸入向量包含一組已選購的產品。 這些產品會放入單一輸出字串中，並以&quot;::&quot;（兩個冒號）分隔。

![](assets/cfg_TransformationType_Merge.png)

因此，如果輸入欄位x-products包含字串值B57481、C46355和Z97123，則生成的輸出字串x-show-products將是B57481::C46355:Z97123.
