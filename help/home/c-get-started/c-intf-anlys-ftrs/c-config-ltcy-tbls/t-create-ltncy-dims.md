---
description: 延遲維度是由父項可計數維度（例如「工作階段」）和時間維度（例如「日」）所建構。
title: 建立延遲維度
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
exl-id: 38b470ef-9409-455b-b2b8-b0391f80b800
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# 建立延遲維度{#create-a-latency-dimension}

延遲維度是由父項可計數維度（例如「工作階段」）和時間維度（例如「日」）所建構。

在Data Workbench中建立延遲表格時，會自動在視覺化檔案(.vw)中新增延遲維度。 您可依照下列步驟編輯表格的延遲維度。

**要編輯延遲維**

1. 開啟在文本編輯器（如記事本）中建立的延遲表。 它位於Data Workbench安裝目錄的「用戶」 > `working profile name` > 「工作」資料夾中。

   定義的延遲維包括如下示例中所示的參數。 （延遲維度的定義可能包含其他參數。） [!DNL line entity = LatencyDim:]表示延遲維度定義的開始。

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. 使用下表作為參考，編輯「名稱」、「級別」、「剪輯」、「時間」、「格式」、「之前時間」或「之後時間」參數的值：

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 對於此參數…… </th> 
      <th colname="col2" class="entry"> 提供此資訊…… </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>名稱 </p> </td> 
      <td colname="col2"> <p>選填。在維標籤或元素上按一下滑鼠右鍵時，出現在內容選單中的延遲維度名稱。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>層級 </p> </td> 
      <td colname="col2"> <p>可計數的維，是延遲維的父級。 範例包括「作業」、「訪客」和「頁面檢視」。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>片段 </p> </td> 
      <td colname="col2"> <p>與延遲維度層級有一對多關係的可計數維度。 不會跨此維度的邊界計算延遲。 例如，如果您指定「頁面檢視」層級和「工作階段」剪輯，則會針對與事件在相同工作階段期間發生的頁面檢視計算延遲。 </p> <p>如需一對多（簡單）維度的詳細資訊，請參閱<i>資料集設定指南</i>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>時間 </p> </td> 
      <td colname="col2"> <p>用於測量延遲維的用時的維。 此維度可以是時間維度，例如日或小時，或可計數的維度，例如訪客、工作階段或頁面檢視。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 格式 </td> 
      <td colname="col2"> <p>選填。指定Data Workbench中延遲視覺化的外觀。 在「格式」參數中，您可以編輯下列值： 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">時間字串。 延遲視覺化中顯示的時間單位，例如日或周。 請務必在變更時間維度時變更時間字串。 </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">偏移。 一個整數，它等於「前一時間」值的負數。 例如，如果「前一時間」為7，則偏移應為-7。 </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>時間之前 </p> </td> 
      <td colname="col2"> <p>計算延遲事件之前的最大時間量（以時間維單位表示）。 如果此值設為0或完全未設定，則僅計算正向延遲。 </p> <p>如果更改此值，請務必更改「格式」(Format)參數中的偏移值：偏移是「前一時間」(Time Before)值的負值。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>時間之後 </p> </td> 
      <td colname="col2"> <p>計算延遲事件之後的最大時間量（以時間維單位表示）。 </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 將[!DNL .vw]檔案保存到User\*working profile name*\Work資料夾。

   以下是預設延遲維度的設定：

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   在下列延遲維度中，每個作業事件的延遲會以小時計算，而「前一時間」則設為零。 因此，只會針對在定義事件後24小時內發生的作業計算延遲。

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
