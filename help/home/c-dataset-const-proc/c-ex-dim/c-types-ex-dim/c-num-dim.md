---
description: 數值維由有序、數值元素組成，且與其父級可計數維度有一對多關係。
solution: Analytics
title: 數值維度
topic: Data workbench
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 數值維度{#numeric-dimensions}

數值維由有序、數值元素組成，且與其父級可計數維度有一對多關係。

您可以將數值維度視為父項維度元素的數值屬性的表示。 例如，如果您使用Web資料，可以定義數值維度「工作階段收入」，此維度會定義「工作階段」維度中每個工作階段的收入金額（以美元為單位）。 每個工作階段都有單一金額的相關收入，但數個工作階段可擁有相同金額的相關收入。 因此，「會話收入」維與「會話」維具有一對多關係。

數值維度常用來定義量度，以求求和值、計算條件的發生次數，或找出最小或最大值。 例如，名為「收入」的量度可能會使用「工作階段收入」維度來定義：sum(Session_Revenue, Session)。 以此方式定義，「收入」量度會提供所選工作階段的總收入。

數值維度不能是其他維度的父項。

數值維由以下參數定義：

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
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
   <td colname="col1"> 剪輯值 </td> 
   <td colname="col2"> 是非。 指定輸入值（在「操作」後）是否被剪切為介於「最小值」和「最大值」之間。 如果「剪輯值」為true，則會將值裁切至該範圍。 如果「剪輯值」為false，則不會傳回父項維度的元素值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於擴展維的注釋。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 輸入欄位有助於建立數字維的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 固定大小 </td> 
   <td colname="col2"> 是非。 控制維中的元素數（基數）。 如果為true，則從「最小值」到「最大值」的所有元素都會包含在尺寸中。 如果為false，則維度的大小會隨著值的新增而增加。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否出現在資料工作台介面中。 依預設，此參數會設為false。 例如，如果維度僅用作度量的基礎，您可以將此參數設為true，以隱藏資料工作台顯示的維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <p>要與指定的「操作」或要計算具體值的輸入值一起使用的值。 </p> <p> 如果此欄位是字串的向量，則會針對向量中的每個元素進行評估。 例如，長度為3的向量和COUNT的運算將增加3。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小值 </td> 
   <td colname="col2"> 最終尺寸結果的下限。 </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大值 </td> 
   <td colname="col2"> 最終尺寸結果的上限。 </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 偏移 </td> 
   <td colname="col2"> 請參閱此表中的縮放。 </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 操作 </td> 
   <td colname="col2"> <p>可用操作如下： </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> 計數：會使用「輸入」欄位中所有符合 <span class="wintitle"> 維度「條件</span> 」之記錄項目的非空白值總數。 如果「輸 <span class="wintitle"> 入</span> 」欄位是向量欄位，則會計算每個記錄項目中非空白值的總數。 </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> 第一個非空白：使用第一個非空白輸入值，不論其是否來自第一個記錄項目。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果值不是數字，則不使用值。 </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> 第一列：使用與父維元素相關的第一個日誌條目的值，即使輸入為空。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果此值為空或不是數字，或者相關日誌條目不符合維的條件，則不使用任何值。 </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> 最後一個非空白：使用最後一個非空白的輸入值，而不論其是否來自最後一個記錄項目。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果值不是數字，則不使用值。 </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> 最後一行：使用與父維元素相關的最後一個日誌條目的值，即使輸入為空。 如果 <span class="wintitle"> Input</span> 是向量欄位，則會使用向量中相關記錄項目的第一列。 如果此值為空或不是數字，或者相關日誌條目不符合維的條件，則不使用任何值。 </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> 總和：系統會使用「輸入」欄位中所有符合 <span class="wintitle"> 維度「條件</span> 」之記錄項目的數值總計。 如果沒有此類日誌條目或找不到數值，則使用數值0。 </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">最小或最大：會使用在「輸入」欄位中 <span class="wintitle"> ，在符合維度「條件</span> 」的所有記錄項目中找到的最小或最大數值。 如果沒有此類日誌條目或沒有數值，則不使用任何值。 </li> 
     </ul> </p> <p> <p>注意： 應指定操作以確保維按預期定義。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數的維度都可以是父項維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 規模 </td> 
   <td colname="col2"> <p>要生成維的序數值，將按如下方式轉換操作結果： </p> <p> （比例*輸入）+偏移 </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如 [!DNL Operation] 果未產生值，或 [!DNL Clip Values] 為false且值不介於和之間 [!DNL Min][!DNL Max]，則數值維度的元素與父維度的元素無關。

此範例說明使用從網站流量收集的事件資料來定義數值維度。 此名為「廣告檢視計數器」的數值維度會計算訪客在指定作業期間看見廣告的次數。 假設所有廣告資源都是從網頁伺服器要求，並且ad=是cs-uri-query的一部分。 在範例中，訪客被展示廣告的次數(COUNT)是興趣值，而非欄位中的實際值。

![](assets/cfg_Transformation_Dim_Numeric.png)

