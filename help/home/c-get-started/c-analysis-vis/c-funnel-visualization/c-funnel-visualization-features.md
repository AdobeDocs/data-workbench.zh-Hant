---
description: 「漏斗」視覺化包含建立漏斗的功能，其中包含多個維度、原始訪客數量、每個步驟的訪客百分比，以及個別範圍。
title: 漏斗功能
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
exl-id: e78dcefe-6f92-45de-9990-0beac09ad82f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 0%

---

# 漏斗功能{#funnel-features}

「漏斗」視覺化包含建立漏斗的功能，其中包含多個維度、原始訪客數量、每個步驟的訪客百分比，以及個別範圍。

以下是漏斗視覺化的基本功能。

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> 第一個元素 </td> 
   <td colname="col2"> 流程中的第一個漏斗步驟。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> 第三個元素 </td> 
   <td colname="col2">流程中的第三個漏斗步驟。 <p><p>注意： 選取的元素不必來自相同的尺寸。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> 流失百分比 </td> 
   <td colname="col2"> 完成定義路徑的百分比顯示在三個範圍中。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> 流失瀏覽器 </td> 
   <td colname="col2">流失箭頭。 按一下右鍵並選擇<span class="uicontrol">添加路徑瀏覽器</span>以查看訪客採用的其他路徑。 </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> 流失百分比 </td> 
   <td colname="col2">描述未完成路徑之使用者的三個流失範圍的百分比。 <p>百分比分為三個範圍： </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> 此步驟前步驟的流失百分比。 </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> 漏斗中第一個步驟的流失百分比。 </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> 根據訪客總數的流失百分比。 </p></td> 
  </tr> 
 </tbody> 
</table>

## 漏斗步驟{#section-96a6732558dd4740b73541844f06d3ef}

漏斗中的磁碟代表導覽中的步驟，圓錐代表從一個步驟到下一個步驟的落差，箭頭代表流失。 按一下錐體，將會選取在該點掉進的使用者，並將其納入目前的工作區篩選。 按一下箭頭將選取流失的訪客。

>[!NOTE]
>
>「漏斗」視覺化限制為8個可套用的步驟。

## 其他漏斗特性和功能{#section-22a3582db8114ca8bce77f50bbbf296a}

* **調整漏斗的剪輯和層級**。從「視覺化」選單選取「漏斗」選項。 建立漏斗後，您可以在標題上按一下滑鼠右鍵，將剪輯段和層級調整至系統中任何可計數的量度。

   ![](assets/funnel_path_browser_9.png)

* **拖曳更多元素**。使用`<Ctrl>` + `<Alt>`鍵，從Dimension表拖放元素至漏斗，將更多元素新增至漏斗。 您可以同時從Dimension表拖曳多個步驟，方法是選取多個項目（使用`<Ctrl>` + click），然後使用`<Ctrl>` + `<Alt>`鍵將它們拖曳至漏斗視覺化。
* **刪除步驟**:以滑鼠右鍵按一下視覺化中的步驟，然後按一下「是」，即可刪除 **元素**。

   ![](assets/funnel_path_browser_4.png)

* **重新排列拖曳至漏斗的步驟**。只要按一下步驟即可選取它，並拖曳至其他位置以重新排列步驟即可。
* **開啟路徑瀏覽器**。透過[新增路徑瀏覽器](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119)功能，您可以進一步瞭解客戶在流程中的流失或流失位置。

* **新增更多步驟**。每個漏斗視覺化最多可新增8個步驟。
* **變更量度**。量度可以變更，因此步驟會計算每個步驟的瀏覽次數或其他量度。 可用選項依資料集而異。
* **以表格式檢視顯示**。以滑鼠右鍵按一下標題以顯示「漏斗視覺化」功能表，然後按一下&#x200B;**[!UICONTROL Show Tabular View]**。 在表格式視圖中，您可以選擇&#x200B;**[!UICONTROL Show Graph View]**&#x200B;以返回漏斗的圖形表示。 要開啟「表格式視圖」，請按一下右鍵標題，然後從菜單中選擇「顯示表格式視圖」。

* **比較序列**。比較兩個類似序列的有效方式是並排顯示其兩個視覺化。 您也可以使用「複製」功能並排顯示表格視圖和圖形視圖。 若要開啟，請在標題上按一下滑鼠右鍵，然後從功能表中選取「複製」。
