---
description: 「關聯和弦」視覺效果可讓您顯示量度、維度和元素之間的比例和關聯，顯示較大的和弦作為關聯性較強的指示。
title: 關聯弦圖視覺效果
uuid: c656ffc8-e45a-44c0-a29b-cdc10dcbd1f2
exl-id: e71394ef-4895-4a3e-912d-d6f56ca8f001
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 1%

---

# 關聯弦圖視覺效果{#association-chord-visualization}

{{eol}}

「關聯和弦」視覺效果可讓您顯示量度、維度和元素之間的比例和關聯，顯示較大的和弦作為關聯性較強的指示。

關聯表將值與Cramer V計算進行比較，而不使用Pearson相關係數，如 [關聯矩陣](/help/home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md) 和 [關聯弦](/help/home/c-get-started/c-analysis-vis/associations-visualization.md) 視覺效果（這些只能比較量度，而關聯表和弦可比較量度、維度和元素）。 關聯和弦還為先前構建的提供另一視圖 [關聯表](../../../home/c-get-started/c-analysis-vis/associations-visualization.md#concept-9d937dda38174875b32095c6eaf22f2f).

**建立關聯和弦**

1. 在工作區中，按一下滑鼠右鍵 **視覺效果>預測分析>關聯弦**.

   將會開啟一個功能表，讓您從清單中選取延伸維度。

   ![](assets/association_chord1.png)

   選中後，將開啟空白的「關聯表」，其中標題中標識了選定Dimension。 ![](assets/association_chord2.png)

1. **選取量度、維度或維度元素**.

   以滑鼠右鍵按一下弦圖視覺效果並選取 **新增量度** 或 **新增Dimension**. 從菜單中選擇要添加到弦的項。

   您也可以從 **[!UICONTROL Finder]** 按一下 **[!UICONTROL Ctrl-Alt]** 並將度量和維度拖曳至和諧。 或者，將維度元素直接從開啟的表格拖曳至弦圖視覺效果。

1. **選擇要關聯的其他度量、維度和元素**.

   選取兩個或兩個以上的值後，圖表會自動重新整理並開始顯示關聯資料。 視需要繼續新增量度，以關聯資料點。

   ![](assets/association_chord.png)

   弦圖視覺效果會顯示以每個區段的面積表示的整體比例。 視需要繼續新增量度/維度/元素，以識別和調查重要關係。

1. **檢視弦圖視覺效果**.

   將滑鼠指標暫留在視覺效果中的每個值上，即可查看關係。

1. **變更設定。** 按一下右鍵和諧視覺效果以開啟功能表，以變更量度、維度或元素將維度顯示為絕對數字或百分比、移除選取的量度或所有量度、編輯顏色和詳細資訊，以及將值匯出至關聯表格。

**要從關聯表建立關聯和弦，請執行以下操作：**

1. 開啟 **關聯表** 視覺效果。
1. 按一下滑鼠右鍵並選取 **匯出弦圖視覺效果**. 將開啟關聯弦圖，其中的值在關聯表中選定。 ![](assets/association_table_to_chord.png)

>[!IMPORTANT]
>
>從包含至少一個度量的關聯和弦圖導出關聯表將導致關聯表的行/列中出現重複元素。 要避免重複的元素，請建立新的關聯表並添加所需的元素，而不是從關聯和弦圖中導出元素。
