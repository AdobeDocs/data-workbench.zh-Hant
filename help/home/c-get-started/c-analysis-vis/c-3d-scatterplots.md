---
description: 3D散布圖會在三維格線上繪製資料維度的元素（例如天數或反向連結網站），其中x、y和z軸代表各種量度。
title: 3D 散佈圖
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
exl-id: 18f18cab-a31b-4ffe-89c5-412a5645af2e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 1%

---

# 3D 散佈圖{#d-scatter-plots}

{{eol}}

3D散布圖會在三維格線上繪製資料維度的元素（例如天數或反向連結網站），其中x、y和z軸代表各種量度。

贊 [散布圖2D](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Scatter_Plots)，此視覺效果在嘗試了解使用不同量度的大量不同項目之間的關係時相當實用。

**若要採用3D散布圖視覺效果：**

1. 開啟新工作區。

   開啟新工作區後，您可能需要按一下 **新增** > **暫時解除鎖定**.
1. 按一下滑鼠右鍵並選取 **視覺效果** > **3D散布圖**.

   功能表清單 **[!UICONTROL Dimensions]** 會開啟。

1. 選取查詢的維度。

   3D散布圖會開啟該維度的預設量度。

   ![](assets/3D_main.png)

   選取 **[!UICONTROL Days]** 菜單在以下軸上顯示以下3D散布圖和這些預設度量： **[!UICONTROL x=Visits]**, **[!UICONTROL y=Retention]**，和 **[!UICONTROL z=Visits]**.

1. 變更量度。 以滑鼠右鍵按一下x、y或z軸中的量度標籤，然後選取 **[!UICONTROL Change Metric]**. 然後為選取的軸選取不同的量度。

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * 將量度拖曳至三軸標籤中的一個，放置該標籤，將選取的軸變更為放置的量度。
   >    * 將量度拖曳至視覺效果的其他位置，並將其放置以變更該軸的半徑量度。
   >    * 將維度拖曳至視覺效果上的任何位置，並將其放置以變更視覺效果的維度。


1. 變更半徑量度。 以滑鼠右鍵按一下頁面頂端的標題（在選取的維度後面加上標題），然後選取 **[!UICONTROL Change Radius Metric]**.

   半徑量度會根據量度選擇來定義繪製點的大小。 散布圖中點的相對位置沒有改變，但視覺效果中的繪製點大小會根據量度值增加。

   ![](assets/3D_change_radius.png)

1. 採用 **[!UICONTROL Orthographic Camera]**. 此選項可讓您根據半徑量度來識別與其真實透視相關的繪圖點，以避免三維失真。

   當3D散布圖首次出現時，它會顯示在三維旋轉投影中，這會導致繪製在更靠近透視的點或虛擬「相機」的點出現一些失真。 （離相機更近的地圖顯示得比離相機更遠旋轉的點大得多。）

   要避免此透視扭曲，可以選取 **[!UICONTROL Orthographic Camera]** 選項，可在標題上按一下滑鼠右鍵並從功能表中選取。 這可讓您以二維表示三維物件。 這會將繪製的點呈現為平坦，並將點顯示為相對於半徑度量，從而減少3維偏移。

1. 從散布圖中選取點。

   * **要刪除點或點組**:按一下該點。
   * **要向您的選擇添加其他點或點組**: **Ctrl** + **按一下** 點或 **Ctrl** + **拖曳** 跨多個點。

   * **從選取項中刪除點或點組**: **Shift** + **按一下** 點或 **Shift** **+** **拖曳** 跨多個點。

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->
