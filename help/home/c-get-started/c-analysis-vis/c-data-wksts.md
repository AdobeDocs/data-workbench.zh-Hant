---
description: 文字或運算式可輸入至工作表的任何儲存格。
title: 在工作表中處理資料
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
exl-id: 40d9211b-8f5c-4051-8f93-638ffacf45bd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 3%

---

# 在工作表中處理資料{#work-with-data-in-worksheets}

文字或運算式可輸入至工作表的任何儲存格。

除非使用[!DNL eval( )]，否則工作表中的所有運算式前面都會加上等號(=)，這會將參考儲存格中的文字視為運算式。

如需量度、維度和篩選語法規則的完整清單，請參閱[查詢語言語法](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。

**要將資料鍵入工作表**

1. 在試算表中的儲存格上按兩下，以進入編輯模式。 所選單元格將突出顯示。
1. 輸入或將所需資料貼入儲存格。

**若要從一個儲存格複製並貼到另一個儲存格**

1. 以滑鼠右鍵按一下包含您要複製之資料的儲存格，然後按一下&#x200B;**[!UICONTROL Copy]**。
1. 以滑鼠右鍵按一下要將複製資料貼入的儲存格，然後按一下&#x200B;**[!UICONTROL Paste]**。

Data Workbench會自動更新新儲存格中的參考，以參考適當的欄和列。

**若要從一組儲存格複製並貼到另一個儲存格**

1. 選取包含您要複製之資料的儲存格。
1. 按一下右鍵包含要複製的資料的單元格，然後按一下&#x200B;**[!UICONTROL Copy]**。
1. 以滑鼠右鍵按一下您要開始貼上複製資料的第一個儲存格，然後按一下&#x200B;**[!UICONTROL Paste]**。 資料會貼入第一個儲存格，並在其下方。

Data Workbench會自動更新新儲存格中的參考，以參考適當的欄和列。

**插入列**

* 按一下右鍵某列，然後按一下&#x200B;**[!UICONTROL Insert Column]**。 新列將插入到選定列的左側。

**刪除列**

* 按一下右鍵要刪除的列，然後按一下&#x200B;**[!UICONTROL Delete Column]**。 欄即會移除。

**要插入行**

* 以滑鼠右鍵按一下某一行，然後按一下&#x200B;**[!UICONTROL Insert Row]**。 新行將插入到選定行的上方。

**刪除行**

* 按一下右鍵要刪除的行，然後按一下&#x200B;**[!UICONTROL Delete Row]**。 該行被刪除。

**調整列大小**

1. 在列標題行中，將游標放在要更改其大小的列右側的分行上。
1. 按一下並拖曳至右側以增加欄的寬度，或拖曳至左側以減少欄的寬度。

**設定儲存格格式**

1. 按一下右鍵單元格，然後按一下&#x200B;**[!UICONTROL Format]**。

   ![](assets/mnu_Worksheet_Format.png)

1. 在可用選項功能表中按一下所需的格式：

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
   <td colname="col2"> <p>將選取的數值格式套用至您的資料，例如時間、日期、百分比或小數。 </p> <p>按一下「<span class="uicontrol">預設</span>」以刪除選定的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>正文 </p> </td> 
   <td colname="col2"> <p>將儲存格內的資料靠左、靠中或靠右對齊。 保留預設對齊。 </p> <p>按一下「<span class="uicontrol">預設</span>」以刪除選定的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>色彩 </p> </td> 
   <td colname="col2"> <p>將所選字型顏色應用於單元格內的資料。 預設字型顏色為白色。 </p> <p>按一下「<span class="uicontrol">預設</span>」以刪除選定的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>指標 </p> </td> 
   <td colname="col2"> <p>使用此儲存格建立量度指標。 如需詳細資訊，請參閱<a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183">建立量度指標</a>。 </p> <p>按一下「<span class="uicontrol">預設</span>」以刪除選定的格式。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>輸入儲存格 </p> </td> 
   <td colname="col2"> <p>將所選儲存格設為輸入儲存格。 如需詳細資訊，請參閱<a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590">建立輸入儲存格</a>。 </p> <p>按一下「<span class="uicontrol">預設</span>」以刪除選定的格式。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 鍵盤快速鍵 {#section-05301f4d2c60418e86902635a7aeee20}

在工作表中，您可以使用許多基本編輯鍵盤快速鍵，這些鍵盤快速鍵可用於任何文本編輯器，如記事本或Microsoft Word。

下表列出了在將資料輸入工作表時可以使用的基本鍵盤快捷鍵。

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
   <td colname="col2"> <p>使用向上、向下、向左和向右箭頭鍵，在工作表中的單元格之間移動。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>將游標放在您選取的儲存格中，即可編輯儲存格。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Enter </p> </td> 
   <td colname="col2"> <p>完成對所選儲存格的編輯。 游標從單元格中刪除，單元格內容反映您的編輯。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>取消編輯您選取的儲存格。 游標從單元格中刪除，單元格內容將恢復到開始編輯之前的狀態。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>刪除 </p> </td> 
   <td colname="col2"> <p>刪除儲存格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>選取儲存格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+c </p> </td> 
   <td colname="col2"> <p>複製儲存格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+x </p> <p>Shift +刪除 </p> </td> 
   <td colname="col2"> <p>複製並移除儲存格的內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+v </p> <p>按住Shift鍵並插入 </p> </td> 
   <td colname="col2"> <p>貼上您已複製到所選儲存格的儲存格內容。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+z </p> </td> 
   <td colname="col2"> <p>還原鍵入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Shift+z </p> </td> 
   <td colname="col2"> <p>取消鍵入。 </p> </td> 
  </tr> 
 </tbody> 
</table>
