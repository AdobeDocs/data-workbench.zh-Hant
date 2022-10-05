---
description: 在實驗中，除了控制組，您還可以定義任意數量的測試組。
solution: Analytics
title: 受控實驗如何運作？
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# 受控實驗如何運作？{#how-do-controlled-experiments-work}

{{eol}}

在實驗中，除了控制組，您還可以定義任意數量的測試組。

執行實驗時，當您網站的所有訪客存取與實驗相關的任何頁面時，即會成為實驗的一部分，可以是測試群組或控制群組的一部分。 訪客會以實驗設定期間定義的比例隨機分配給您的實驗群組。

受控實驗是使用 [!DNL Sensor] 安裝在Web群集中每個內容伺服器上的軟體。 當內容伺服器收到請求時， [!DNL Sensor] 隨機選取測試群組的訪客，並將其頁面請求重新導向至實驗內容。 當 [!DNL Sensor] 選擇訪客以查看測試內容，地址欄會繼續列出最初請求的URI，但訪客會被路由到測試URI。 由於此程式在伺服器應用程式中內部進行，因此使用者不知道何時正在接受測試，這是進行無偏倚實驗的重要考量。

[!DNL Sensor] 將測試URI（而不是向用戶顯示的原始URI）傳遞到日誌檔案，以便在分析中使用。

實驗結果可以很方便地用 [!DNL Insight] 來判斷您所測試的實驗假設是否正確。

>[!NOTE]
>
>Adobe強烈建議您協調受控實驗，並使用組織中負責設定和維護分析資料集之人員的輸入進行。
