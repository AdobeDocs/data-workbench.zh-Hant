---
description: Data Workbench中的長條圖現在包含多個圖表中多個量度的回歸比較。
title: 迴歸分析圖
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
exl-id: bfc76c4a-edd5-41fe-b875-c199ea3beab5
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---

# 迴歸分析圖{#regression-analysis-graph}

Data Workbench中的長條圖現在包含多個圖表中多個量度的回歸比較。

[橫條](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) 圖Data Workbench可讓您將一個圖表中的量度重新轉換為另一個圖表中的量度。如果您有多個圖表，您可以比較量度（作為獨立變數）與評估其他量度（作為相依變數）的圖表。 這可讓您判斷一個相依變數（先建立的量度）與一系列其他變更量度（與已建立的相依量度的回歸）之間的關係強度。

圖表視覺效果上的回歸分析可讓分析人員執行「若則」案例。 例如，如果造訪次數增加至此層級，此增加對收入會有何影響？

**設定回歸分析**

1. 選取圖形作為回歸比較的相依量度。

   在圖形上按一下滑鼠右鍵，然後選擇「**設定為回歸**&#x200B;的基本度量」。

   ![](assets/c_graph_regression_1.png)

1. 將其他度量圖表設為獨立變數。

   按一下滑鼠右鍵量度，然後為其他量度選取&#x200B;**[!UICONTROL Regress with `<base metric name>`]**。

   ![](assets/c_graph_regression.png)

1. 以滑鼠右鍵按一下圖表以上下移動長條，即可檢視回歸。

   如果以滑鼠右鍵按一下圖表中的特定值，您就可以根據向上或向下的值查看每個量度的回歸比率。

   ![](assets/c_graph_regression_2.png)

   例如，如果我的頁面檢視次數減少至86,041，則其他量度將有下列值：瀏覽次數12,183次，訪客次數12,028次。

   ![](assets/c_graph_regression_3.png)

   如果「依瀏覽次數的訪客」值增加至26,141，則其他量度將是「瀏覽次數」為26,560，而「頁面檢視次數」為189,091。
