---
description: 受控實驗是test，使您能夠將從實驗樣本組獲得的結果與從標準控制組獲得的結果進行比較。
solution: Analytics
title: Data Workbench控制實驗
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Data Workbench控制實驗{#data-workbench-controlled-experiments}

受控實驗是test，使您能夠將從實驗樣本組獲得的結果與從標準控制組獲得的結果進行比較。

站點使您能夠實施、測量和分析受控實驗及其結果，因為它們與網站的不同方面相關。 這樣，在花費大量時間或金錢來全面實施擬議的更改之前，您就可以test關於網站效能改善的假設。

>[!NOTE]
>
>只有在資料集中才能分析站點實驗，其中唯一使用的訪問者識別方法是 [!DNL Sensor] 設定永久cookie方法。 運行在J2EE伺服器（JBoss、Tomcat、WebLogic和WebSphere）上的感測器不支援受控實驗。 有關詳細資訊，請參閱以下部分。

使用「站點」，您可以實施A/B、A/B/A和多變數控制實驗，以收集足夠的test資料，從而提供統計上準確的資料，以便對假設進行詳細評估，而不會影響當前網站的效能。
