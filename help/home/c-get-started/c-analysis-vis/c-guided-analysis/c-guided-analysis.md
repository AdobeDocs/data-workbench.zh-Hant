---
description: 引導式分析視覺效果提供提示，供您根據在工作區中所做的選取進行進一步分析。
title: 引導式分析
uuid: 01ed8207-3a14-45ac-8a1d-4e17ac39bb94
exl-id: c19b52b6-52db-455e-adde-8b2400aae006
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---

# 引導式分析{#guided-analysis}

{{eol}}

引導式分析視覺效果提供提示，供您根據在工作區中所做的選取進行進一步分析。

此視覺效果可協助您識別哪些維度可提供您更多資訊，亦即與您的選取項目最具關聯性的維度。 Adobe應用程式中的引導式分析視覺效果會顯示與資料集相關的維度，如下所示 [!DNL Site] 引導式分析視覺效果。

![](assets/vis_GuidedAnalysis.png)

>[!NOTE]
>
>如果維度名稱以紅色顯示，資料集中並未定義該名稱。

當您在工作區中進行選取時，引導式分析視覺效果會在左側顯示勾號，並在維度右側顯示點，以顯示哪些維度提供最相關的資訊：

* **勾號** 以統計顯著方式識別其值與基準不同的維度（亦即，選取項目與基準之間的差異不是因為隨機機會）。
* **點** 指示選擇與基準不同的程度。 第一個點代表U統計值，第二個點代表V統計值。 請參閱 [了解統計測量](../../../../home/c-get-started/c-analysis-vis/c-guided-analysis/c-stat-measures.md#concept-ba2c7f417f384dc0a3438fcb6e268708). 點越亮、越大，差異越大，基於您選擇的維度的資訊就越相關（即，更亮、更大的點代表更有用的資訊）。
