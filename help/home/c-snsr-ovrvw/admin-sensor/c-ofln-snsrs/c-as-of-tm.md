---
description: 當資料工作台伺服器從該源接收資料時，它會感知到資料源，如感測器。
title: 瞭解「截止」時間
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 瞭解「截止」時間{#understanding-as-of-time}

當資料工作台伺服器從該源接收資料時，它會感知到資料源，如感測器。

截止時間保證[!DNL data workbench server]具有其所知所有資料源的資料。

假設我們有一組[!DNL Sensors]會傳送資料至[!DNL data workbench server]:WEB1、WEB2和WEB3。 當[!DNL data workbench server]從這些[!DNL Sensors]接收並處理資料時，它會自動預期來自這些來源的資料。 截止時間表示[!DNL data workbench server]上次從這三個源接收資料的時間。

實際上，[!DNL data workbench server]只關心「截止時間」，而不關心「牆時間」或牆上鐘的時間。 [!DNL data workbench server]只將時間作為截止時間。 這對於報告而言尤其重要，因為它保證報告始終根據截止時間運行，這可確保只包含部分資料的報告永遠不能發送給系統的最終用戶。

[!DNL data workbench server]使用從發射器傳送的資料來提供截止時間，不論是從網站收集的實際資料或您的[!DNL Sensors]傳送的定期心率。 這些心率有兩個用途：

1. 在[!DNL Sensor]和[!DNL data workbench server]之間保持HTTP/1.1持久連接開啟。

1. 若要在未收集網站流量並傳送至[!DNL data workbench server]的情況下，將「截止」時間保持為最新。
