---
description: 引導式分析視覺化可根據您在工作區中所做的選擇，提供進一步分析的提示。
title: 引導式分析
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# 引導式分析{#guided-analysis}

引導式分析視覺化可根據您在工作區中所做的選擇，提供進一步分析的提示。

此視覺化功能可協助您識別哪些維度可為您提供更多資訊，即與您選取範圍最緊密關聯的維度。 Adobe應用程式中的引導式分析視覺化會顯示與資料集相關的維度，如下列[!DNL Site]引導式分析視覺化中所示。

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>如果維度名稱以紅色顯示，則不會在資料集中定義。

在工作區中進行選取時，引導分析視覺化會在維度的左側顯示核取標籤，並在右側顯示點，以顯示哪些維度提供最相關的資訊：

* **檢** 查標籤以統計上顯著方式識別值與基準不同的維度（亦即，選擇與基準之間的差異並非因隨機機會而產生）。
* **Dots** 表示選擇與基準不同的程度。第一點代表U統計值，第二點代表V統計值。 請參閱[瞭解統計測量](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708)。 點越亮、越大，差異越大，根據您的選取範圍建立維度的資訊也越相關（即，點越亮、點越大代表更有用的資訊）。
