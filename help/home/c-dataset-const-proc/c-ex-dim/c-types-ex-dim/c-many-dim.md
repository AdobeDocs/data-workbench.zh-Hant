---
description: 多對多維度與其父項可數維度有多對多關係。
title: 多對多維度
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
exl-id: 02d1a21c-a5b4-4b58-8089-9b9c68a7b1d1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 3%

---

# 多對多維度{#many-to-many-dimensions}

{{eol}}

多對多維度與其父項可數維度有多對多關係。

您可以將多對多維度視為其父維度中每個元素之一組值的表示。 例如，多對多維度「搜尋片語」是工作階段層級維度（具有工作階段的父項）。 它代表與「工作階段」維度中每個工作階段相關聯的搜尋片語集。 單個搜尋片語可用於任何數量的工作階段，而單個工作階段可包含零個或多個搜尋片語。 因此，「搜尋片語」維度與「工作階段」維度有多對多關係。

多對多維度由下列參數定義：

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
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
   <td colname="col2"> 在Data Workbench中對使用者顯示的維度描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。延伸維度的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 建立父欄位和輸入欄位值之間關係的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否顯示在Data Workbench介面中。 此參數預設會設為false。 例如，如果維度僅作為量度的基礎，您可以將此參數設為true，以便在Data Workbench顯示中隱藏維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <p>與父維（父）相關的值。 如果此欄位是字串的向量，則向量的每個元素都與父項有各自的關係。 </p> <p> <p>注意：如果父維的某個元素的每個日誌條目的輸入值為空，則多對多維度的任何元素都不會與父維的該元素相關。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父級 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數維度都可以是父維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明使用從網站流量收集的事件資料來定義多對多維度。 此多對多維度（名為「選取的產品」）會將工作階段與訪客在該工作階段期間購買的產品相關。 x-products欄位包含值向量，每個值都與頁面檢視相關聯，而頁面檢視又與工作階段相關聯。

![](assets/cfg_Transformation_Dim_ManytoMany.png)

透過建立此轉換，您可以在Data Workbench中建立視覺效果，以描繪所選產品維度與涉及每個產品之工作階段數之間的關係。
