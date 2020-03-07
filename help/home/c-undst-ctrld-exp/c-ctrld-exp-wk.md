---
description: 在實驗中，除了控制群組外，您還可以定義任意數量的測試群組。
solution: Insight,Analytics
title: 控制實驗如何運作？
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 控制實驗如何運作？{#how-do-controlled-experiments-work}

在實驗中，除了控制群組外，您還可以定義任意數量的測試群組。

當實驗執行時，您網站的所有訪客一旦存取任何參與實驗的頁面，即會作為測試群組或控制群組的一部分，成為實驗的一部分。 訪客會以實驗設定期間定義的比例隨機分配給您的實驗群組。

控制實驗是使用安裝在 [!DNL Sensor] Web叢集中每個內容伺服器上的軟體來實作。 當內容伺服器收到請求時，會隨 [!DNL Sensor] 機選取您測試群組的訪客，並將其頁面請求重新導向至實驗內容。 當選 [!DNL Sensor] 取訪客以檢視測試內容時，位址列會繼續列出最初請求的URI，但訪客會被路由至測試URI。 由於此程式是在伺服器應用程式內部進行，所以使用者不知道他們何時會受到測試，這是進行無偏見實驗的重要考量。

[!DNL Sensor] 將測試URI（而非顯示給用戶的原始URI）傳遞至用於分析的日誌檔案。

實驗結果可以很容易地用來 [!DNL Insight] 判斷您測試的實驗假設是否正確。

>[!NOTE]
>
>Adobe強烈建議您協調並執行受控實驗，並應由組織中負責設定和維護分析資料集的個人提供意見。

