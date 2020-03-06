---
description: 3D散布圖會在三維格線上繪製資料維度（例如天數或反向連結網站）的元素，其中x、y和z軸代表各種度量。
solution: Analytics
title: 3D散布圖
topic: Data workbench
uuid: 5e23547c-dbb4-490c-94bc-0731deee612e
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 3D散布圖{#d-scatter-plots}

3D散布圖會在三維格線上繪製資料維度（例如天數或反向連結網站）的元素，其中x、y和z軸代表各種度量。

與散 [布圖2D類似](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Scatter_Plots)，此視覺化在嘗試瞭解使用不同度量的大量不同項目之間的關係時十分有用。

**若要使用3D散布圖視覺化：**

1. 開啟新工作區。

   開啟新工作區後，您可能需要按一下「新增 **>暫** 時解除鎖定 ****」。
1. 以滑鼠右鍵按一下並選 **取「視覺化** > **3D散布圖」**。

   將會開啟功能 **[!UICONTROL Dimensions]** 表清單。

1. 選擇查詢的維。

   3D散布圖會開啟該維度的預設量度。

   ![](assets/3D_main.png)

   選取功 **[!UICONTROL Days]** 能表會在下列軸上顯示下列3D散布圖及這些預設度量： **[!UICONTROL x=Visits]**、 **[!UICONTROL y=Retention]**&#x200B;和 **[!UICONTROL z=Visits]**。

1. 變更量度。 在x、y或z軸中的量度標籤上按一下滑鼠右鍵，然後選取 **[!UICONTROL Change Metric]**。 然後為選取的軸選取不同的量度。

   ![](assets/3D_change.png)

   >[!IMPORTANT]
   >
   >
   >    
   >    
   >    * 將量度拖曳至三個軸標籤中的一個，並將其拖曳，將選取的軸變更為拖曳的量度。
   >    * 將量度拖曳至視覺化上的其他位置，並將其拖曳以變更該軸的半徑量度。
   >    * 將維度拖曳至視覺化上的任意位置，並將其拖曳以變更視覺化的維度。


1. 變更半徑量度。 以滑鼠右鍵按一下頁面頂端的標題（標題在選取的維度後），然後選取 **[!UICONTROL Change Radius Metric]**。

   半徑量度會根據量度選擇來定義繪製點的大小。 點的相對位置在散布圖中不會變更，但視覺化中繪製的點大小會根據量度值而增加。

   ![](assets/3D_change_radius.png)

1. 請使用 **[!UICONTROL Orthographic Camera]**。 此選項可讓您根據半徑量度識別與其真實透視相關的繪圖點，以避免三維扭曲。

   當「3D散布圖」首次出現時，會以三維旋轉投影顯示，這會造成繪製在離透視更近的點或虛擬「相機」的扭曲。 （離相機較近的圖片顯示得比遠離相機旋轉的點大得多。）

   若要避免此透視扭曲，您可以在標 **[!UICONTROL Orthographic Camera]** 題上按一下滑鼠右鍵，然後從選單中選取選項。 這可讓您以二維表示三維物件。 這會將繪製的點轉換為平整點，並相對於半徑度量顯示點，從而減少3維偏移。

1. 從散布圖中選取點。

   * **要移除點或點組**:按一下該點。
   * **要向所選內容添加另一點或點組**:Ctrl **+** click **a point or** Ctrl +拖 **曳****** 多個點。

   * **要從選取範圍中移除點或點組**:Shift **+按一** 下點或 **Shift** + **拖曳** 數個 ******** 點。

<!-- <a id="section_9C30F9799F1440F09278327002E6B47A"></a> -->

