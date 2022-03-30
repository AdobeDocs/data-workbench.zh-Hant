---
description: 在實驗中，除了控制組外，還可以定義任意數量的test組。
solution: Analytics
title: 受控實驗如何運作？
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# 受控實驗如何運作？{#how-do-controlled-experiments-work}

在實驗中，除了控制組外，還可以定義任意數量的test組。

當實驗運行時，所有訪問您網站的訪問者只要訪問參與實驗的任何頁面，即會成為實驗的一部分，無論是作為test組還是控制組的一部分。 訪問者隨機分配到您的實驗組，其比例在實驗配置中定義。

實驗結果表明： [!DNL Sensor] 安裝在Web群集中每個內容伺服器上的軟體。 當內容伺服器接收請求時， [!DNL Sensor] 隨機為您的test組選擇訪問者，並將其頁面請求重定向到實驗內容。 當 [!DNL Sensor] 選擇訪問者以查看test內容，地址欄繼續列出最初請求的URI，但訪問者被路由到testURI。 由於此過程在伺服器應用程式內部進行，因此用戶不知道他們何時被測試，這是進行無偏的試驗的一個重要考慮因素。

[!DNL Sensor] 將testURI（而不是顯示給用戶的原始URI）傳遞給日誌檔案，以供分析使用。

實驗結果可用於分析 [!DNL Insight] 來判斷你所測試的實驗假設是否正確。

>[!NOTE]
>
>Adobe強烈建議，在組織中負責配置和維護分析資料集的那些人員的投入下，協調並執行受控實驗。
