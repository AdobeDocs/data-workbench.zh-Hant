---
description: 數值維度由有序的數值元素組成，且與其父項可數維度間具有一對多關係。
title: 數值維度
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
exl-id: 69a4dfa6-8402-4c2b-8b04-e6e1a0fd5ccb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 2%

---

# 數值維度{#numeric-dimensions}

數值維度由有序的數值元素組成，且與其父項可數維度間具有一對多關係。

您可以將數值維度視為父維度元素之數值屬性的表示法。 例如，若您使用網路資料，您可以定義數值維度「工作階段收入」，此維度會為「工作階段」維度中的每個工作階段以美元為單位定義收入金額。 每個工作階段都有單一的相關收入金額，但數個工作階段可以有相同數量的相關收入。 因此，「工作階段收入」維度與「工作階段」維度間具有一對多關係。

數值維度常用來定義量度，以求加總值、計算條件的發生次數，或找出最小值或最大值。 例如，名為「收入」的量度可使用「工作階段收入」維度來定義：sum(Session_Revenue, Session)。 以此方式定義，「收入」量度會提供所選工作階段的總收入。

數值維度不能是其他維度的父項。

數值維度由下列參數定義：

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
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
   <td colname="col1"> 剪輯值 </td> 
   <td colname="col2"> True 或 False. 指定輸入值（在操作後）是否被剪切為介於最小值和最大值之間。 如果「剪輯值」為true，則值被剪切到該範圍。 如果「剪輯值」為false，則不返回父維的元素的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。延伸維度的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 輸入欄位協助建立數值維度的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 固定大小 </td> 
   <td colname="col2"> True 或 False. 控制維中的元素數（基數）。 如果為true，則從「最小值」到「最大」的所有元素都包含在維中。 如果為false，則維度的大小會隨著新增值而增加。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否顯示在Data Workbench介面中。 此參數預設會設為false。 例如，如果維度僅作為量度的基礎，您可以將此參數設為true，以便在Data Workbench顯示中隱藏維度。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <p>要與指定的Operation一起使用的值，或要計算其發生次數的輸入值。 </p> <p> 如果此欄位是字串的向量，則會針對向量中的每個元素進行評估。 例如，長度為3的向量和COUNT的操作使計數增加3。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小值 </td> 
   <td colname="col2"> 最終維度結果的下限。 </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大值 </td> 
   <td colname="col2"> 最終維度結果的上限。 </td> 
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
      <li id="li_CAEE9167D45540BEAC538345F250B509"> 計數：會使用<span class="wintitle">輸入</span>欄位中所有符合維度條件之記錄項目的非空白值總數。 如果<span class="wintitle">輸入</span>欄位是向量欄位，則計算每個日誌條目中非空值的總數。 </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> 第一個非空白：無論輸入值是否來自第一個日誌條目，都會使用第一個非空白輸入值。 如果<span class="wintitle">輸入</span>為向量欄位，則使用相關日誌條目的向量中的第一行。 如果值不是數字，則不會使用任何值。 </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> 第一行：系統會使用與父維度元素相關的第一個記錄項目的值，即使輸入為空白亦然。 如果<span class="wintitle">輸入</span>為向量欄位，則使用相關日誌條目的向量中的第一行。 如果此值為空或不是數字，或相關記錄項目不符合維度的條件，則不會使用任何值。 </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> 最後一個非空白：系統會使用最後一個非空白輸入值，而不論其是否來自最後一個記錄項目。 如果<span class="wintitle">輸入</span>為向量欄位，則使用相關日誌條目的向量中的第一行。 如果值不是數字，則不會使用任何值。 </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> 最後一行：系統會使用與上層維度元素相關的最後一個記錄項目的值，即使輸入為空白亦然。 如果<span class="wintitle">輸入</span>為向量欄位，則使用相關日誌條目的向量中的第一行。 如果此值為空或不是數字，或相關記錄項目不符合維度的條件，則不會使用任何值。 </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> 總和：會使用<span class="wintitle">輸入</span>欄位中所有符合維度條件之記錄項目的數值總計。 如果沒有此類日誌條目或未找到數值，則使用數值0。 </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">最小值或最大值：會使用<span class="wintitle">輸入</span>欄位中所有符合維度條件之記錄項目的最小值或最大值。 如果沒有此類日誌條目或沒有數值，則不使用任何值。 </li> 
     </ul> </p> <p> <p>注意： 您應指定一個操作，以確保維按預期的方式定義。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父級 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數維度都可以是父維度。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 規模 </td> 
   <td colname="col2"> <p>要生成維的序數值，將轉換操作的結果如下： </p> <p> (刻度*輸入+偏移 </p> </td> 
   <td colname="col3"> 1.0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>如果[!DNL Operation]未產生任何值，或[!DNL Clip Values]為false且值不介於[!DNL Min]和[!DNL Max]之間，則數值維度的任何元素都不與父維度的元素相關。

此範例說明使用從網站流量收集的事件資料來定義數值維度。 此名為「廣告檢視計數器」的數值維度會計算訪客在指定工作階段期間看見廣告的次數。 假設是所有播發資源都是從Web伺服器請求的，其中ad=是cs-uri-query的一部分。 在此範例中，訪客收到廣告的次數(COUNT)是感興趣的值，而非欄位中的實際值。

![](assets/cfg_Transformation_Dim_Numeric.png)
