---
description: 「關聯表」視覺效果可讓您使用Cramer V演算法將量度與量度、維度和維度元素建立關聯。
title: 關聯表視覺效果
uuid: 4563c336-3377-4929-8694-8c0d00866825
exl-id: 3fc2c025-d369-45ed-8c9e-eb4a0ac412b7
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 1%

---

# 關聯表視覺效果{#association-table-visualization}

「關聯表」視覺效果可讓您使用Cramer V演算法將量度與量度、維度和維度元素建立關聯。

關聯表將值與Cramer V計算進行比較，而不使用[關聯矩陣](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/correlation-analysis/c-correlation-analysis.html)和[關聯弦](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-chord-visualization.html)視覺化中使用的皮爾遜相關係數（這些只能比較度量，而關聯表和[關聯弦](../../../home/c-get-started/c-analysis-vis/associations-chord.md#concept-51d0bda998474dd5946cc2a9b8393445)可以比較度量、維度和元素）。

## 建立關聯表 {#section-87ed12ccc1af4196a1b6534e621c4cbb}

「關聯表」會比較可數或不可數維度的量度。 您可以修改表格，透過挑選顏色來反白標示視覺效果中的關聯，或將其轉譯為文字圖、熱度圖或兩者。

1. 開啟關聯表。

   按一下右鍵[!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Association Table]。

   ![](assets/association_table.png)

1. 選取延伸維度，即點進、點擊、產品、造訪或訪客維度。 「關聯表」(Association Table)將開啟，角落中標識的延伸維度，行和列中均放置其關聯度量。

   ![](assets/association_table1.png)

   關聯表使用Cramer V作為對稱關聯，導致選定的度量、維和元素值反映在關聯表的列和行中。 例如，選取&#x200B;**Product**&#x200B;延伸維度時，會在表格的列和欄中使用&#x200B;**[!UICONTROL Visits]**&#x200B;量度作為相關量度，因此會產生完美但無用的比較(1.00)，因為比較值相同。

1. 向關聯表添加更多值。

   在列或行中按一下右鍵，然後選擇&#x200B;**添加度量**&#x200B;或&#x200B;**添加Dimension**。 您也可以從&#x200B;**Finder**&#x200B;面板拖曳量度和維度。 Dimension元素也可從開啟的表格拖放至表格視覺效果。

   ![](assets/association_table2.png)

   >[!NOTE]
   >
   >關聯表中允許10行和10列。
