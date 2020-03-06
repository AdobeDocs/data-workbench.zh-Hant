---
description: 「關聯和弦」視覺化可讓您顯示量度、維度和元素之間的比例和關聯，並顯示較大的和弦作為更強關聯的指示。
title: 關聯和弦視覺化
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關聯和弦視覺化{#association-chord-visualization}

「關聯和弦」視覺化可讓您顯示量度、維度和元素之間的比例和關聯，並顯示較大的和弦作為更強關聯的指示。

「關聯表」會將值與Cramer的V計算比較，而不使用 [Correlation Matrix](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) and [](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) Correlation Chord視覺化中採用的Pearson相關係數（這些只能比較度量，而「關聯表」和「Chord」可以比較度量、維度和元素）。 「關聯和弦」(Associations Chord)還為先前構建的「關聯表」( [Associations Table](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f))提供另一視圖。

**建立關聯和弦**

1. 在工作區中，以滑鼠右鍵按一下「 **視覺化>預測分析>關聯弦**」。

   將開啟一個菜單，允許您從清單中選擇擴展維。

   ![](assets/association_chord1.png)

   選取後，空白的「關聯表格」將會開啟，並在標題中標識選取的「維度」。 ![](assets/association_chord2.png)

1. **選取量度、維度或維度元素**。

   以滑鼠右鍵按一下和弦視覺化，然後選 **取「新增量度** 」 **或「新增維度」**。 從菜單中選擇要添加到弦的項目。

   您也可以按一下並拖曳量度和維度至 **[!UICONTROL Finder]** 弦， **[!UICONTROL Ctrl-Alt]** 從中拖曳量度和維度。 或直接從開啟的表格拖曳維度元素至弦視覺化。

1. **選擇其他要關聯的量度、維度和元素**。

   在選取兩個或兩個以上的值後，圖表會自動重新整理並開始顯示關聯資料。 視需要繼續新增量度，以關聯資料點。

   ![](assets/association_chord.png)

   「弦」視覺化會顯示每個區段的面積所代表的整體比例。 視需要繼續新增量度／維度／元素，以識別並調查重要關係。

1. **檢視Chord視覺化**。

   將滑鼠指標暫留在視覺化中的每個值上，即可查看關係。

1. **變更設定.** 以滑鼠右鍵按一下和弦視覺化開啟功能表，以變更量度、維度或元素以絕對數字或百分比顯示尺寸、移除選取的量度或所有量度、編輯顏色和詳細資料，以及將值匯出至關聯表格。

**要從關聯表構建關聯和弦：**

1. 開啟關聯 **表格視覺化** 。
1. 以滑鼠右鍵按一下並選取「 **匯出弦視覺化」**。 關聯和弦圖將開啟，其中的值在關聯表中選擇。 ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>從包含至少一個度量的關聯弦圖導出關聯表將導致在關聯表的行／列中產生重複的元素。 為避免重複的元素，請建立新的關聯表格並新增所需的元素，而非從關聯弦圖中匯出元素。

