---
description: 簡單維度與其父項可數維度有一對多關係。
title: 簡單維度
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
exl-id: 2acad750-7c48-40f1-8130-ab056ac8bf0d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 1%

---

# 簡單維度{#simple-dimensions}

簡單維度與其父項可數維度有一對多關係。

簡單維度一律為可數維度的子項。 您可以將簡單維度視為其父維中元素屬性的表示。 例如，若您使用的是網頁資料，則可以定義「訪客反向連結」維度，這是父維度為「訪客」的簡單維度。 它代表「訪客」維度中每個訪客的第一個HTTP反向連結。 「訪客」維度中的每個訪客只有一個訪客反向連結，但許多訪客可以有相同的訪客反向連結。 因此，「訪客反向連結」維度與「訪客」維度有一對多關係。

簡單維由以下參數定義：

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> Data Workbench中顯示的維度描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
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
   <td colname="col2"> 與父維（父）相關的值欄位。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 載入檔案 </td> 
   <td colname="col2"> <p>選填。關係的可用值檔案。 在以下任一情況下，可使用載入檔案： </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> 這些值有您要在Data Workbench顯示中保留的特定排序順序。 例如，您可能想要建立一個季度維度，其元素（季別）一律依時間順序顯示。 </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> 您想要為資料中找不到但需要顯示在Data Workbench顯示中的值建立位置保持器。 </li> 
     </ul> </p> <p> 如果遇到檔案中不存在的值，則會在Data Workbench中檢視時，將其新增至值的結尾。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>可用操作如下： </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> 第一個非空白：無論輸入值是否來自第一個日誌條目，都會使用第一個非空白輸入值。 如果「輸入」是向量欄位，則使用相關日誌條目的向量中的第一行。 </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> 第一行：系統會使用與父維度元素相關的第一個記錄項目的值，即使輸入為空白亦然。 如果「輸入」是向量欄位，則使用相關日誌條目的向量中的第一行。 如果此值為空或不是數字，或相關記錄項目不符合維度的條件，則不會使用任何值。 </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> 最後一個非空白：系統會使用最後一個非空白輸入值，而不論其是否來自最後一個記錄項目。 如果「輸入」是向量欄位，則使用相關日誌條目的向量中的第一行。 </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> 最後一行：系統會使用與上層維度元素相關的最後一個記錄項目的值，即使輸入為空白亦然。 如果「輸入」是向量欄位，則使用相關日誌條目的向量中的第一行。 如果此值為空或不是數字，或相關記錄項目不符合維度的條件，則不會使用任何值。 </li> 
     </ul> </p> <p> <p>注意： 如果「操作」為特定日誌條目不產生值或空白值，則父維的相應元素將與簡單維的「無」元素相關。 </p> </p> <p> 您應指定一個操作，以確保維按預期的方式定義。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父級 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數維度都可以是父維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明使用從網站流量收集的事件資料和載入檔案來定義簡單維度。

以民調問答網站訪客最喜愛的女孩ScoutCookie為例。 網頁會擷取此投票，並將其傳回至名稱值配對的favoritecookie中的Web伺服器。 每位訪客只會計算一次投票，但訪客可以改變主意，並視需要再次投票。 這是一對多的關係：一位訪客可以有多張選票，但每張選票僅與一位訪客相關聯。 因此，維度的父項是訪客（每位訪客只投一票），而操作是「最後一列」（這樣他們就能改變主意並再次投票）。

所有類型的Cookie都必須有預留位置，才能在Data Workbench顯示中顯示沒有得票的Cookie類型。 基於這些原因，已定義載入檔案，其中包含可選取的Cookie類型清單。 此檔案的內容儲存在名為[!DNL cookietypes.txt]的檔案中，如下所示：

動物珍寶

焦糖美食

檸檬酥油

花生醬

短麵包

薄薄薄

最終維度的定義如下所示：

![](assets/cfg_Transformation_Dim_Simple.png)
