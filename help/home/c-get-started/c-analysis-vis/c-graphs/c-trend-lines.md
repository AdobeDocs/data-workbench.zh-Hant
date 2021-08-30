---
description: 趨勢線可讓您覆蓋圖形以比較和解讀資料。
title: 趨勢線
uuid: b1d81973-2181-4507-a0a5-adf5eeb9f926
exl-id: 3e7e9218-49b2-4877-a4bd-318b838089e8
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 1%

---

# 趨勢線{#trend-lines}

趨勢線可讓您覆蓋圖形以比較和解讀資料。

與[散布圖](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/c-scat-plots.html)視覺效果類似，您現在可以在圖表視覺效果上設定趨勢線，以根據線性、指數、冪或多項式線來顯示變更率。 趨勢線功能可讓您在圖形上覆蓋趨勢線，最常是在時間維度上。

例如，在此圖表比較中，我們可以看到造訪呈上升趨勢，但訂單呈下降趨勢。

![](assets/trend_line.png)

新增趨勢線的方式

1. 開啟圖表，然後以滑鼠右鍵按一下左上角的量度名稱。
1. 按一下&#x200B;**[!UICONTROL Trend Lines]**&#x200B;並從選項中選取。

   ![](assets/trend_line_graph.png)

   您可以選取趨勢線以&#x200B;**簡單線性**、**指數**、**冪**&#x200B;或&#x200B;**多項式**&#x200B;形式顯示在圖形上。 多項式將建立多項式回歸趨勢線。 簡單線性將建立趨勢線作為沿著回歸線的變化率。 指數計算趨勢線，其形式為y = b*exp(a*x)，冪形式為y = b*x`<sup>a</sup>`。

   趨勢將在圖形上計算和呈現，並且標注將開啟，顯示趨勢方程式的詳細資訊。

   ![](assets/trend_line_detail.png)
