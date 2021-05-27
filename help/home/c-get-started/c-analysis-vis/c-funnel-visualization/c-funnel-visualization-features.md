---
description: 漏斗視覺效果包含的功能可讓您建立漏斗，其中包含多個維度、原始訪客數、每個步驟的訪客百分比，以及個別的範圍。
title: 漏斗功能
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# 漏斗功能{#funnel-features}

漏斗視覺效果包含的功能可讓您建立漏斗，其中包含多個維度、原始訪客數、每個步驟的訪客百分比，以及個別的範圍。

以下是漏斗視覺效果的基本功能。

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> 第一個元素 </td> 
   <td colname="col2"> 此程式中的第一個漏斗步驟。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> 第三個元素 </td> 
   <td colname="col2">此程式中的第三個漏斗步驟。 <p><p>注意： 所選元素不必來自相同的維。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> 流失百分比 </td> 
   <td colname="col2"> 完成三個範圍中顯示的定義路徑的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> 流失瀏覽器 </td> 
   <td colname="col2">流失箭頭。 按一下滑鼠右鍵並選取<span class="uicontrol">新增路徑瀏覽器</span> ，查看訪客採用的其他路徑。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> 流失百分比 </td> 
   <td colname="col2">說明未完成路徑之使用者的三個流失範圍的百分比。 <p>百分比分為三個範圍： </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> 此步驟之前步驟的流失百分比。 </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> 漏斗中第一個步驟的流失百分比。 </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> 根據訪客總數的流失百分比。 </p></td> 
  </tr> 
 </tbody> 
</table>

## 漏斗步驟{#section-96a6732558dd4740b73541844f06d3ef}

漏斗中的磁碟代表導覽中的步驟，錐體代表從一個步驟到下一個步驟的落體，箭頭代表流失。 按一下錐體將選取在該點掉進的使用者，並將其納入目前的工作區篩選器中。 按一下箭頭即可選取流失的訪客。

>[!NOTE]
>
>漏斗視覺效果有8個可套用步驟的限制。

## 其他漏斗特徵和功能{#section-22a3582db8114ca8bce77f50bbbf296a}

* **調整漏斗的剪輯和級別**。從「視覺效果」功能表選取「漏斗」選項。 建立漏斗後，您可以按一下滑鼠右鍵標題，將剪輯和級別調整為系統中任何可數量度。

   ![](assets/funnel_path_browser_9.png)

* **拖曳更多元素**。使用`<Ctrl>` + `<Alt>`鍵，將元素從Dimension表格拖放至漏斗，以新增更多元素。 您可以選取多個項目（使用`<Ctrl>` +按一下），然後使用`<Ctrl>` + `<Alt>`鍵將多個步驟拖曳至「漏斗」視覺效果，即可同時從Dimension表格拖曳多個步驟。
* **刪除步驟**:以滑鼠右鍵按一下視覺效果中的步驟，然後按一下「是」以刪除 **元素**。

   ![](assets/funnel_path_browser_4.png)

* **重新排列拖曳至漏斗的步驟**。只需按一下步驟來選取它，然後將其拖曳至其他位置以重新排列步驟。
* **開啟路徑瀏覽器**。您可以透過[新增路徑瀏覽器](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119)功能，查看客戶在程式中落後或流失的詳細資訊。

* **新增更多步驟**。每個漏斗視覺效果最多可新增八個步驟。
* **變更量度**。量度可以變更，以便步驟計算每個步驟的造訪次數或其他某些量度。 可用選項依資料集而異。
* **以表格檢視顯示**。以滑鼠右鍵按一下標題以顯示「漏斗視覺效果」功能表，然後按一下&#x200B;**[!UICONTROL Show Tabular View]**。 在表格檢視中，您可以選取&#x200B;**[!UICONTROL Show Graph View]**&#x200B;以返回漏斗的圖形表示。 要開啟「表格視圖」，請按一下右鍵標題，然後從菜單中選擇「顯示表格視圖」。

* **比較序列**。比較兩個類似序列的有效方式是並排顯示其兩個視覺效果。 您也可以使用「複製」功能並排顯示表格檢視和圖形檢視。 若要開啟，請以滑鼠右鍵按一下標題，然後從功能表選取「複製」 。
