---
description: Data Workbench包含內建維度。
title: 內建維度
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
exl-id: c08a487d-60b8-4db7-8776-7ae1b9f1f27c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 14%

---

# 內建維度{#built-in-dimensions}

{{eol}}

Data Workbench包含內建維度。

下表列出Data Workbench可用的內建維度：

<table id="table_40796088B3484F98889859C59D525AD7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 名稱 </th> 
   <th colname="col2" class="entry"> 詳細資料 </th> 
   <th colname="col3" class="entry"> 層級 </th> 
   <th colname="col4" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 無 </td> 
   <td colname="col2"> 衍生 </td> 
   <td colname="col3"> 不適用 </td> 
   <td colname="col4">具有與所有維度的所有元素相關的單一元素「」。 依「無」來評估量度，就像依無維度來評估量度。 <p>此 <span class="filepath"> 篩選[None=""]</span> 等於 <span class="filepath"> [True]</span>. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一（隱藏） </td> 
   <td colname="col2"> 數值 </td> 
   <td colname="col3"> 不適用 </td> 
   <td colname="col4">元素"1"也具有序數值 <span class="filepath"> = 1</span>，與所有維度的所有元素相關。 「單一」維度通常用來透過以下語法建構計數： <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>
