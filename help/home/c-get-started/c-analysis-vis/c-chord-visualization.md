---
description: 弦圖視覺效果可讓您顯示量度之間的比例和關聯，顯示較大的弦作為較強關聯的指示。
title: 弦圖視覺效果
uuid: 3f322f58-f8f5-4d91-bdf8-4b5f9d7fb072
exl-id: d712f7b3-de2f-4ca4-a1bf-a2e4d42a084e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# 弦圖視覺效果{#chord-visualization}

{{eol}}

弦圖視覺效果可讓您顯示量度之間的比例和關聯，顯示較大的弦作為較強關聯的指示。

「弦圖」視覺效果可讓您查看量度之間的關聯，讓您新增並輕鬆評估可能的關聯。 它也提供先前建置之任何檢視的其他檢視 [關聯矩陣](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html). 使用弦圖視覺效果時，您無法識別量度之間的正相關或負相關，只有關聯存在。 在某些情況下，可透過套用計數器量度來識別直接或反向關係。

1. **開啟&#x200B;**[!UICONTROL Chord]**視覺效果**.

   在工作區中，按一下滑鼠右鍵 [!DNL Visualization > Predictive Analytics > Chord].

1. **從功能表選取Dimension**.

   將會開啟空白視覺效果，供您選取維度。 維度名稱會出現在空白弦圖視覺效果的頂端。

   >[!NOTE]
   >
   >如果工作區中已開啟「關聯矩陣」，您也可以將其呈現為「弦圖」視覺效果。

1. **選擇要關聯的量度**.

   從 **[!UICONTROL Finder]** 按一下 **[!UICONTROL Ctrl-Alt]** 將度量從表格拖曳至圖表。 選取兩個或多個量度後，圖表會自動重新整理並開始顯示關聯資料。 視需要繼續新增量度，以建立資料點的關聯。

   ![](assets/chord_drag_metric.png)

   弦圖視覺效果會顯示以每個區段的面積表示的整體比例。 視需要繼續新增量度，以識別和調查重要關係。

   ![](assets/chord_selected.png)

1. **檢視弦圖視覺效果**.

   將滑鼠指標暫留在視覺效果中的每個量度上，即可查看關係。 在此範例中，您可以看到件數與大部分其他量度( **造訪期間** 量度)。

   ![](assets/chord_visualization_1.png)

   當您將游標暫留在 **造訪期間** 「弦圖」視覺效果上的量度，您會發現所有其他量度之間幾乎沒有或最薄弱的關聯。

   ![](assets/chord_visualization_2.png)

1. **變更設定。** 以滑鼠右鍵按一下「弦圖」視覺效果，開啟功能表以變更維度、以絕對數字或百分比顯示維度、移除選取的量度或所有量度、編輯顏色和詳細資料，以及將值匯出至「關聯矩陣」。

   ![](assets/chord_menu.png)
