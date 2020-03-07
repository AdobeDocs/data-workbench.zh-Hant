---
description: 多對多維度與其父項可計數維度有多對多關係。
solution: Analytics
title: 多對多維度
topic: Data workbench
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 多對多維度{#many-to-many-dimensions}

多對多維度與其父項可計數維度有多對多關係。

您可以將多對多維度視為父項維度中每個元素之一組值的表示。 例如，多對多維度「搜尋片語」是「作業階段」層級的維度（具有「作業階段」的父項）。 它表示與「會話」維中每個會話關聯的搜索片語集。 單一搜尋片語可用於任何數目的作業，而單一作業可包含零或多個搜尋片語。 因此，「搜尋片語」維度與「工作階段」維度有多對多關係。

多對多維由以下參數定義：

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
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
   <td colname="col2"> 資料工作台中使用者所看見之維度的描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於擴展維的注釋。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應建立父欄位與輸入欄位值之間關係的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否出現在資料工作台介面中。 依預設，此參數會設為false。 例如，如果維度僅用作度量的基礎，您可以將此參數設為true，以隱藏資料工作台顯示的維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <p>與父項維（父項）相關的值。 如果此欄位是字串的向量，則向量的每個元素都與父項有其專屬的關係。 </p> <p> <p>注意： 如果父維的元素的每個日誌條目的輸入值為空，則多對多維的任何元素都不會與父維的元素相關。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數的維度都可以是父項維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明使用從網站流量收集的事件資料來定義多對多維度。 此多對多維度（稱為「選取的產品」）與訪客在該作業期間購買的產品相關。 x-products欄位包含值的向量，其中每個值都與頁面檢視相關聯，而頁面檢視又與工作階段相關聯。

![](assets/cfg_Transformation_Dim_ManytoMany.png)

透過建立此類轉換，您可以在資料工作台中建立視覺化，以描繪所選產品維度與涉及每個產品之工作階段數之間的關係。
