---
description: 資料工作台包含內建維度。
solution: Analytics
title: 內建尺寸
topic: Data workbench
uuid: 0aabbc52-266d-46c1-a4b3-dd575c0f2c72
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 內建尺寸{#built-in-dimensions}

資料工作台包含內建維度。

下表列出資料工作台的可用內建維度：

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
   <td colname="col4">具有與所有維度的所有元素相關的單一元素""。 將量度評估為「無」，就像是在無維度上評估量度。 <p>篩 <span class="filepath"> 選器[None=""]</span> 等 <span class="filepath"> 同於[True]</span>。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一個（隱藏） </td> 
   <td colname="col2"> 數值 </td> 
   <td colname="col3"> 不適用 </td> 
   <td colname="col4">元素"1"也具有序數值= 1 <span class="filepath"></span>，它與所有維的所有元素相關。 One dimension通常用於使用下列語法來建構計數： <p><span class="filepath"> sum(one,Countable_Dimension)</span></p></td> 
  </tr> 
 </tbody> 
</table>

