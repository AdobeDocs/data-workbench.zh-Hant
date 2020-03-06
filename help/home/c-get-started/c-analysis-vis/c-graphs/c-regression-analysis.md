---
description: 資料工作台中的長條圖現在包含多個圖表中多個度量的回歸比較。
title: 回歸分析圖
uuid: 8512890e-f42b-4dce-826a-2b4bf2a215f4
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Regression Analysis Graph{#regression-analysis-graph}

資料工作台中的長條圖現在包含多個圖表中多個度量的回歸比較。

[「資料工作台](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/graphs/c-graphs.html) 」中的長條圖可讓您將一個圖表中的量度重新轉換為另一個圖表中的量度。 如果您有多個圖形，您可以比較度量（作為獨立變數）與評估其他度量（作為相依變數）的圖形。 這可讓您判斷一個相依變數（先建立的量度）與一系列其他變更量度（與已建立的相依量度回歸）之間的關係強度。

圖形視覺化上的回歸分析可讓分析者執行「假設」藍本。 例如，如果瀏覽次數增加到此層級，此次增加會對收入產生什麼影響？

**設定回歸分析**

1. 選取圖形作為回歸比較的相依量度。

   在圖形上按一下滑鼠右鍵，然後選取「 **設定為回歸的基本量度」**。

   ![](assets/c_graph_regression_1.png)

1. 將其他量度圖表設為獨立變數。

   以滑鼠右鍵按一下量度，並選取 **[!UICONTROL Regress with `<base metric name>`]** 其他量度。

   ![](assets/c_graph_regression.png)

1. 在圖表上按滑鼠右鍵以上下移動列，以檢視回歸。

   如果您以滑鼠右鍵按一下圖表以取得特定值，則可依向上或向下的值查看每個度量的回歸率。

   ![](assets/c_graph_regression_2.png)

   例如，如果我的「頁面檢視」減少為86,041，則其他量度會有下列值：12,183次瀏覽與12,028次瀏覽的訪客。

   ![](assets/c_graph_regression_3.png)

   如果「依瀏覽次數的訪客」值增加至26,141，則其他度量將是「瀏覽次數為26,560」,「頁面檢視次數」將是189,091。

