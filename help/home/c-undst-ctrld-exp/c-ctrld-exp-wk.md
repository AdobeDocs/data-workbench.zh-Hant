---
description: 在實驗中，除了控制群組外，您還可以定義任意數量的測試群組。
solution: Analytics,Analytics
title: 受控實驗如何運作？
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# 受控實驗如何運作？{#how-do-controlled-experiments-work}

在實驗中，除了控制群組外，您還可以定義任意數量的測試群組。

當實驗執行時，您網站的所有訪客一旦存取任何參與實驗的頁面，即會作為測試群組或控制群組的一部分，成為實驗的一部分。 訪客會以實驗設定期間定義的比例隨機分配給您的實驗群組。

控制實驗是使用[!DNL Sensor]軟體實現的，該軟體安裝在Web群集中的每個內容伺服器上。 當內容伺服器收到請求時，[!DNL Sensor]會隨機選取測試群組的訪客，並將其頁面請求重新導向至實驗內容。 當[!DNL Sensor]選取訪客以檢視測試內容時，位址列會繼續列出最初請求的URI，但訪客會被路由至測試URI。 由於此程式是在伺服器應用程式內部進行，所以使用者不知道他們何時會受到測試，這是進行無偏見實驗的重要考量。

[!DNL Sensor] 將測試URI（而非顯示給用戶的原始URI）傳遞至用於分析的日誌檔案。

使用[!DNL Insight]可輕鬆分析實驗結果，以判斷您所測試的實驗假設是否正確。

>[!NOTE]
>
>Adobe強烈建議使用組織中負責設定和維護分析資料集的人員所提供的意見來協調和執行受控實驗。
