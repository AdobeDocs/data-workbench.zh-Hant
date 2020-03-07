---
description: 簡單維度與其父項可計數維度有一對多關係。
solution: Analytics
title: 簡單尺寸
topic: Data workbench
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 簡單尺寸{#simple-dimensions}

簡單維度與其父項可計數維度有一對多關係。

簡單維度永遠是可計數維度的子系。 您可以將簡單尺寸視為其父尺寸中元素屬性的表示。 例如，如果您使用Web資料，可以定義「訪客反向連結」維度，此維度是具有父級維度的簡單維度。 它代表「訪客」維度中每個訪客的第一個HTTP反向連結。 「訪客」維度中的每個訪客只有一個訪客反向連結，但許多訪客可以有相同的訪客反向連結。 因此，「訪客反向連結」維度與「訪客」維度有一對多關係。

簡單尺寸由以下參數定義：

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> 維度在資料工作台中顯示的描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於擴展維的注釋。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 建立父欄位與輸入欄位值之間關係的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否出現在資料工作台介面中。 依預設，此參數會設為false。 例如，如果維度僅用作度量的基礎，您可以將此參數設為true，以隱藏資料工作台顯示的維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 與父維（父）相關的值欄位。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 載入檔案 </td> 
   <td colname="col2"> <p>選填。關係的可用值檔案。 在下列任一情況下，您都會使用載入檔案： </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> 這些值具有您想在資料工作台顯示中保留的特定排序順序。 例如，您可能想要建立一個季度維度，其元素（年份的季度）一律以時間順序顯示。 </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> 您想要為資料中找不到但需要顯示在資料工作台顯示中的值建立預留位置。 </li> 
     </ul> </p> <p> 如果遇到檔案中未顯示的值，在資料工作台中檢視時，會將其新增至值的結尾。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>可用操作如下： </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> 第一個非空白：使用第一個非空白輸入值，不論其是否來自第一個記錄項目。 如果「輸入」是向量欄位，則會使用相關記錄項目的向量中的第一列。 </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> 第一列：使用與父維元素相關的第一個日誌條目的值，即使輸入為空。 如果「輸入」是向量欄位，則會使用相關記錄項目的向量中的第一列。 如果此值為空或不是數字，或者相關日誌條目不符合維的條件，則不使用任何值。 </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> 最後一個非空白：使用最後一個非空白的輸入值，而不論其是否來自最後一個記錄項目。 如果「輸入」是向量欄位，則會使用相關記錄項目的向量中的第一列。 </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> 最後一行：使用與父維元素相關的最後一個日誌條目的值，即使輸入為空。 如果「輸入」是向量欄位，則會使用相關記錄項目的向量中的第一列。 如果此值為空或不是數字，或者相關日誌條目不符合維的條件，則不使用任何值。 </li> 
     </ul> </p> <p> <p>注意： 如果「操作」沒有為特定日誌條目生成任何值或空值，則父維的相應元素將與簡單維的「無」元素相關。 </p> </p> <p> 應指定操作以確保維按預期定義。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數的維度都可以是父項維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例說明使用從網站流量收集的事件資料和載入檔案來定義簡單維度。

以網站訪客最愛的Girl Scout Cookie民調問答為例。 網頁會擷取此投票，並將其傳回名稱——值配對favoritecookie中的網頁伺服器。 每個訪客只會計算一次投票，但訪客可以改變主意，並視需要再次投票。 這是一對多的關係：一位訪客可以有多張投票，但每張投票僅與一位訪客關聯。 因此，維度的父代是訪客（每位訪客僅投一票），而操作是「最後一列」（如此，他們就可以改變想法並再次投票）。

所有類型的Cookie都必須有預留位置，如此才能在資料工作台中顯示沒有投票的Cookie類型。 基於這些原因，已定義包含可選Cookie類型清單的載入檔案。 此檔案的內容保存在名為的檔案中， [!DNL cookietypes.txt]如下所示：

動物珍寶

焦糖美食

檸檬酥油

花生醬小餅

短餅

薄薄薄薄

最終尺寸定義如下：

![](assets/cfg_Transformation_Dim_Simple.png)

