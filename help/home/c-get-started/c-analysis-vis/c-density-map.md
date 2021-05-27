---
description: 密度圖視覺效果會在方形圖中以陰影矩形顯示元素。
title: 密度圖
uuid: c13cecee-f322-4757-aa90-12039173ff9f
exl-id: da37d954-cadb-42a6-a44b-9b38c0354a5d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 1%

---

# 密度圖{#density-map}

密度圖視覺效果會在方形圖中以陰影矩形顯示元素。

矩形的大小取決於元素值，其中較大的值由較大面積的矩形表示。 此視覺效果類似圓餅圖，可讓您快速查看哪些元素構成所選維度的最大百分比。

![](assets/density_map_day_visits.png)

要建立密度圖，請執行以下操作：

1. 開啟新工作區。

   開啟新工作區後，您可能需要按一下「**新增** > **暫時解除鎖定**」。
1. 按一下 **[!UICONTROL Visualization]** > **[!UICONTROL Density Map]**.

1. 從菜單中選擇&#x200B;**[!UICONTROL Dimension]**。

   例如，選擇&#x200B;**[!UICONTROL Time]** > **[!UICONTROL Days]**。

   相反地，選取「**[!UICONTROL Time]** > **[!UICONTROL Hours]**」會提供更多值較小的元素，並顯示為較小的矩形。

   >[!NOTE]
   >
   >您會想要根據需求選取包含多個元素的維度。 目前限制為每個維度最大的元素200個。

1. 您可以開啟「**[!UICONTROL Visualization]** > **[!UICONTROL Table]**」，並從表格中選取要在地圖中顯示的各元素，以變更維度檢視。

   ![](assets/density_map_day_selections.png)

   地圖會回應表格中的選取項目。

1. 將滑鼠游標暫留在小型元素上時，會以滑鼠游標附近出現的文字顯示其名稱和值。
1. 按一下右鍵並選擇&#x200B;**[!UICONTROL Mask]**，然後選擇一個選項來蒙版元素。

   ![](assets/density_map_day_mask.png)

   要顯示所有被遮罩的節點，請選擇&#x200B;**[!UICONTROL Unhide All]**。

1. 以滑鼠右鍵按一下並選取&#x200B;**[!UICONTROL Spotlight]**，然後選擇選項來選取焦點元素。 焦點光源可讓您反白標示範圍中的元素並將其變暗。
1. 將顏色圖例新增至工作區。 您可以使用色彩圖例來識別地圖中的值。

   您可以將色彩圖例新增至工作區，而節點會根據其他資料維度變更色彩。
1. 以滑鼠右鍵按一下對應標題，然後從功能表選取，以變更維度或量度。

   ![](assets/density_map_change_dim.png)

1. 按一下右鍵單元格並選擇&#x200B;**[!UICONTROL Add Callout]**&#x200B;以添加圖說文字。 您可以從功能表中選取不同類型或視覺效果。

   ![](assets/density_map_callout.png)

1. 與所有視覺效果一樣，您可以在標題列上方按一下滑鼠右鍵，即可顯示「關閉」、「儲存」、「匯出至Microsoft Excel」、「訂單」、「複製」、「最小化」和「無邊框」等基本命令，以顯示無邊框的視覺效果。

   ![](assets/density_map_export.png)

1. 「密度圖」可讓您選取和取消選取與其他視覺效果類似的多個元素：

* 按一下左鍵以選取元素。
* Ctrl +按一下以選取多個元素。
* Shift +按一下以取消選取元素。
* 在選取的元素內按一下滑鼠右鍵以開啟功能表。 然後選擇&#x200B;**[!UICONTROL Deselect]**&#x200B;或&#x200B;**[!UICONTROL Deselect All]**&#x200B;以清除所選元素。

## 其他選項 {#section-d77defb012424de4a7ced8e5c93115bc}

以滑鼠右鍵按一下「密度圖」，開啟包含下列選項的功能表：

<table id="table_3ADA85031C834792BFD041E186962A41"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 新增 註解 </td> 
   <td colname="col2">在視覺效果中新增文字或圖形作為圖說文字，以進一步識別或說明元素。 <p>您也可以根據「密度圖」中選取的元素，選取空白的量度圖例、表格、折線圖或散布圖。 接著，您可以視需要將量度和維度新增至這些空白視覺效果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 遮色片 </td> 
   <td colname="col2">遮罩選項可讓您隱藏選取的元素。 按一下右鍵以顯示「遮色片」選項。 <p><span class="uicontrol"> 隱藏此元素</span> — 選擇此選項以遮罩已選取的單個元素。 </p> <p><span class="uicontrol"> 隱藏選定項</span>(Hide Selected) — 選擇此選項以遮罩已選取的多個元素。 </p> <p><span class="uicontrol"> 顯示排名最前</span> — 選擇此選項，根據「密度圖」中的值，僅顯示排名前100、50、25或10的元素。 </p> <p><span class="uicontrol"> 顯示底部</span> — 根據「密度圖」中的值，選擇此選項只顯示底部100、50、25或10個頂部元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 精選 </td> 
   <td colname="col2"> 焦點光源可讓您反白標示範圍中的元素並將其變暗。 按一下右鍵以開啟選項菜單。 <p><span class="uicontrol"> 顯示排名最前</span> — 選擇此選項，僅根據「密度圖」中的值反白顯示排名最前的100、50、25或10個元素。 </p> <p><span class="uicontrol"> 顯示底部</span> — 根據「密度圖」中的值，選擇此選項僅反白顯示底部100、50、25或10個頂部元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>取消選擇 </p> <p>取消選擇全部 </p> </td> 
   <td colname="col2"> <p> 選取這些命令以取消選取當前元素（如果已選取），或取消選取選取的所有元素。 </p> </td> 
  </tr> 
 </tbody> 
</table>
