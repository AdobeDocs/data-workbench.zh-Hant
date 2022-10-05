---
description: 非正規維度與其父項可數維度有一對一的關係。
title: 非正規維度
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
exl-id: 0c4fad38-bc7c-4b63-98ec-c9121e576a36
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# 非正規維度{#denormal-dimensions}

{{eol}}

非正規維度與其父項可數維度有一對一的關係。

每當所需維度包含其父項之每個元素的唯一元素時，您就會定義非正規維度。 例如， [!DNL EMail Address] 是父項為訪客的非正規維度。 每個訪客都有電子郵件地址，而「電子郵件地址」維度中的每個元素都是單一訪客的電子郵件地址。 即使兩個訪客具有相同的電子郵件地址，這些地址仍是「電子郵件地址」維度的不同元素。

您可以在任何表格視覺效果、詳細資料表格或建立篩選器時使用非正規維度。 此外，您也可以搭配Data Workbench伺服器的區段匯出功能使用非正規維度來匯出欄位的值(例如 [!DNL Tracking ID] 或 [!DNL EMail Address])，而有許多值。 因為您要匯出的任何區段資料都必須定義為設定檔中的維度，因此您必須建立非正規維度，以儲存欄位資料的原始字串。

>[!NOTE]
>
>在表格或其他預期一般維度的視覺效果中使用非正規維度時，會自動建立衍生的非正規維度。 衍生的非正規維度與父維度有一對多關係。

如需詳細資料表格視覺效果和篩選器的相關資訊，請參閱 *Data Workbench使用手冊*. 如需區段匯出的相關資訊，請參閱 *Data Workbench使用手冊*.

>[!NOTE]
>
>非正規維度在查詢時間和磁碟空間方面可能非常昂貴。 具有父項的非正規維度 [!DNL Page View]而一個50位元組的平均輸入字串，可能會在一個典型、大型資料集中的緩衝區中新增25 GB資料，相當於約13個簡單或數值的頁面檢視維度，或約125個工作階段層級維度。 若未仔細評估效能影響，請勿將非正規維度新增至資料集。

非正規維度由下列參數定義：

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
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
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 與父維（父）相關的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 標準化元素 </td> 
   <td colname="col2"> 一個效能調整參數，它指定要在系統記憶體中儲存其名稱的維元素的數量。 將此參數設定為較高值會導致非正規維度使用更多RAM，但會導致更快速的查詢。 預設值為 16383。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>可用操作如下： </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> 第一個非空白：無論輸入值是否來自第一個日誌條目，都會使用第一個非空白輸入值。 若 <span class="wintitle"> 輸入</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> 第一行：系統會使用與父維度元素相關的第一個記錄項目的值，即使輸入為空白亦然。 若 <span class="wintitle"> 輸入</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果此值為空或不是數字，或相關記錄項目不符合維度的條件，則不會使用任何值。 </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> 最後一個非空白：系統會使用最後一個非空白輸入值，而不論其是否來自最後一個記錄項目。 若 <span class="wintitle"> 輸入</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> 最後一行：系統會使用與上層維度元素相關的最後一個記錄項目的值，即使輸入為空白亦然。 若 <span class="wintitle"> 輸入</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果此值為空或不是數字，或相關記錄項目不符合維度的條件，則不會使用任何值。 </li> 
     </ul> </p> <p> <p>注意：如果「操作」未產生值，則使用空白值("")。 </p> </p> <p> 您應指定一個操作，以確保維按預期的方式定義。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父級 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數維度都可以是父維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

此範例中顯示的非正規維度會將欄位x-trackingid中的所有資料視為輸入，並將其納入名為訪客ID的維度中。 對於您建立的訪客區段，您可以匯出「訪客ID」維度中的資料（以及任何其他定義的維度）。

![](assets/cfg_Transformation_Dim_Denormal.png)
