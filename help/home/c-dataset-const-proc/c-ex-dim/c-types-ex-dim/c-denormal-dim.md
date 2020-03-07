---
description: 非正規維度與其父項可計數維度有一對一的關係。
solution: Analytics
title: 非正規維度
topic: Data workbench
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 非正規維度{#denormal-dimensions}

非正規維度與其父項可計數維度有一對一的關係。

只要所需維度包含其父項之每個元素的唯一元素，您就會定義非正規維度。 例如， [!DNL EMail Address] 是父代為「訪客」的非正規維度。 每個訪客都有電子郵件地址，而「電子郵件地址」維度中的每個元素都是單一訪客的電子郵件地址。 即使兩個訪客具有相同的電子郵件地址，這些地址仍是「電子郵件地址」維度的不同元素。

您可以在任何表格視覺化、詳細表格或建立篩選器中使用非正規維度。 此外，您還可以搭配資料工作台伺服器的區段匯出功能使用非正規維度，以匯出具有大量值的欄位( [!DNL Tracking ID][!DNL EMail Address]例如或)的值。 由於您要匯出的任何區段資料都必須定義為描述檔中的維度，因此您必須建立非正規維度，以儲存欄位資料的原始字串。

>[!NOTE]
>
>在表格或其他需要一般維度的視覺化中使用非正規維度時，會自動建立衍生的非正規維度。 衍生的非正規維度與父項維度有一對多關係。

如需詳細表格視覺化和篩選器的詳細資訊，請參閱資料工作台使用指南中的「分 *析視覺化」一章*。 如需區段匯出的詳細資訊，請參閱資料工作台使用指南中的「設定介 *面和分析功能」一章*。

>[!NOTE]
>
>非正規維度在查詢時間和磁碟空間方面可能非常昂貴。 具有父項和50位元組平 [!DNL Page View]均輸入字串的非正規維度，可能會在典型大型資料集的緩衝區中新增25 GB資料，相當於約13個簡單或數值頁面檢視維度，或約125個作業階層維度。 在未仔細評估效能影響的情況下，切勿將非正規維度新增至資料集。

非正規尺寸由下列參數定義：

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
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
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 與父項維（父項）相關的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 標準化元素 </td> 
   <td colname="col2"> 一個效能調整參數，它指定其名稱要儲存在系統儲存器中的維元素的數量。 將此參數設為較高值，會導致非正規維度使用較多RAM，但會導致查詢更快速。 預設值為 16383。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>可用操作如下： </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> 第一個非空白：使用第一個非空白輸入值，不論其是否來自第一個記錄項目。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> 第一列：使用與父維元素相關的第一個日誌條目的值，即使輸入為空。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果此值為空或不是數字，或者相關日誌條目不符合維的條件，則不使用任何值。 </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> 最後一個非空白：使用最後一個非空白的輸入值，而不論其是否來自最後一個記錄項目。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> 最後一行：使用與父維元素相關的最後一個日誌條目的值，即使輸入為空。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果此值為空或不是數字，或者相關日誌條目不符合維的條件，則不使用任何值。 </li> 
     </ul> </p> <p> <p>注意： 如果「工序」未產生值，則使用空白值("")。 </p> </p> <p> 應指定操作以確保維按預期定義。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數的維度都可以是父項維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例中顯示的非正規維度會將欄位x-trackingid中的所有資料視為輸入，並將其納入名為「訪客ID」的維度中。 對於您所建立的訪客區段，您可以匯出「訪客ID」維度（以及任何其他定義的維度）中的資料。

![](assets/cfg_Transformation_Dim_Denormal.png)

