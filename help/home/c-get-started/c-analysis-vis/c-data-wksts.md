---
description: 文字或運算式可輸入至工作表的任何儲存格。
solution: Analytics
title: 在工作表中處理資料
topic: Data workbench
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 在工作表中處理資料{#work-with-data-in-worksheets}

文字或運算式可輸入至工作表的任何儲存格。

除非使用，否則工作表中的所有運算式前面都會加上等號(=) [!DNL eval( )]，這會將參考儲存格中的文字視為運算式。

如需度量、維度和篩選語法規則的完整清單，請參 [閱查詢語言語法](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。

**要將資料鍵入工作表，請執行以下操作：**

1. 按兩下試算表中的儲存格，以進入編輯模式。 選定的單元格將加亮顯示。
1. 輸入或貼入儲存格中所需的資料。

**從一個儲存格複製並貼至另一個儲存格**

1. 按一下右鍵包含要複製的資料的單元格，然後按一下 **[!UICONTROL Copy]**。
1. 按一下右鍵要將複製的資料貼上到的單元格，然後按一下 **[!UICONTROL Paste]**。

資料工作台會自動更新新儲存格中的參考，以參考適當的欄和列。

**從一組儲存格複製並貼至其他儲存格**

1. 選擇包含要複製的資料的單元格。
1. 按一下右鍵包含要複製的資料的單元格，然後按一下 **[!UICONTROL Copy]**。
1. 按一下右鍵要開始將複製的資料貼上到的第一個單元格，然後按一下 **[!UICONTROL Paste]**。 資料會貼至第一個儲存格及其下方。

資料工作台會自動更新新儲存格中的參考，以參考適當的欄和列。

**要插入列**

* 按一下右鍵列，然後按一下 **[!UICONTROL Insert Column]**。 新列將插入到選定列的左側。

**刪除列**

* 按一下右鍵要刪除的列，然後按一下 **[!UICONTROL Delete Column]**。 列即被刪除。

**要插入行**

* 按一下右鍵一行，然後按一下 **[!UICONTROL Insert Row]**。 新行將插入到選定行的上方。

**刪除行**

* 按一下右鍵要刪除的行，然後按一下 **[!UICONTROL Delete Row]**。 行被刪除。

**要調整列的大小**

1. 在列標題行中，將游標置於要更改其大小的列右側的分隔線上。
1. 按一下並拖曳至右側以增加欄的寬度，或拖曳至左側以減少欄的寬度。

**格式化儲存格**

1. 按一下右鍵單元格，然後按一下 **[!UICONTROL Format]**。

   ![](assets/mnu_Worksheet_Format.png)

1. 在可用選項的功能表中按一下所需格式：

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 功能表選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>數字 </p> </td> 
   <td colname="col2"> <p>將選取的數值格式套用至您的資料，例如時間、日期、百分比或小數。 </p> <p>按一 <span class="uicontrol"> 下「預設</span> 」以移除選取的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>對齊 </p> </td> 
   <td colname="col2"> <p>將儲存格內的資料靠左、靠中或靠右對齊。 預設對齊方式為左。 </p> <p>按一 <span class="uicontrol"> 下「預設</span> 」以移除選取的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>色彩 </p> </td> 
   <td colname="col2"> <p>將選取的字型顏色套用至儲存格內的資料。 預設字型顏色為白色。 </p> <p>按一 <span class="uicontrol"> 下「預設</span> 」以移除選取的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>指標 </p> </td> 
   <td colname="col2"> <p>使用此儲存格建立量度指標。 如需詳細資訊，請參 <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> 閱建立量度指標</a>。 </p> <p>按一 <span class="uicontrol"> 下「預設</span> 」以移除選取的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>輸入儲存格 </p> </td> 
   <td colname="col2"> <p>將選取的儲存格設為輸入儲存格。 如需詳細資訊，請參閱建 <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> 立輸入儲存格</a>。 </p> <p>按一 <span class="uicontrol"> 下「預設</span> 」以移除選取的格式。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 鍵盤快速鍵 {#section-05301f4d2c60418e86902635a7aeee20}

在工作表中，您可以使用許多基本編輯鍵盤快速鍵，這些快速鍵可用於任何文字編輯器，例如記事本或Microsoft Word。

下表列出在將資料輸入工作表時，您可使用的基本鍵盤快速鍵。

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 快速鍵 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>方向鍵 </p> </td> 
   <td colname="col2"> <p>使用向上、向下、向左和向右方向鍵，在工作表中的儲存格間移動。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>將游標置於所選儲存格中，以編輯儲存格。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enter </p> </td> 
   <td colname="col2"> <p>完成對所選單元格的編輯。 游標會從儲存格中移除，而儲存格內容會反映您的編輯。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>取消對所選單元格的編輯。 游標會從儲存格中移除，儲存格內容會回復為您開始編輯之前的狀態。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除 </p> </td> 
   <td colname="col2"> <p>刪除儲存格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>選擇單元格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+c </p> </td> 
   <td colname="col2"> <p>複製儲存格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+x </p> <p>Shift+Delete </p> </td> 
   <td colname="col2"> <p>複製並移除儲存格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+v </p> <p>Shift+Insert </p> </td> 
   <td colname="col2"> <p>將已複製到選定單元格的單元格內容貼上。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+z </p> </td> 
   <td colname="col2"> <p>還原輸入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Shift+z </p> </td> 
   <td colname="col2"> <p>重做輸入。 </p> </td> 
  </tr> 
 </tbody> 
</table>

