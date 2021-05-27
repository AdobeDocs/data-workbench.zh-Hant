---
description: 受控實驗是一種測試，可讓您比較從實驗樣本組獲得的結果和從標準控制組獲得的結果。
solution: Analytics,Analytics
title: Data Workbench受控實驗
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Data Workbench受控實驗{#data-workbench-controlled-experiments}

受控實驗是一種測試，可讓您比較從實驗樣本組獲得的結果和從標準控制組獲得的結果。

網站可讓您實作、測量和分析受控實驗及其結果，使其與網站的不同層面相關。 這樣可讓您在花大量時間或金錢全面實施建議的變更之前，先測試關於改善網站效能的假設。

>[!NOTE]
>
>只有在使用中唯一的訪客身分識別方法是[!DNL Sensor]設定永久性Cookie方法的資料集中，才能分析網站實驗。 在J2EE伺服器（JBoss、Tomcat、WebLogic和WebSphere）上運行的感測器不支援受控實驗。 如需詳細資訊，請參閱下節。

您可以使用「網站」來實作A/B、A/B/A及多變數受控實驗，以收集足夠的測試資料，以提供統計上精確的資料用於詳細評估假設，而不會影響目前的網站效能。
