---
description: 當Data Workbench伺服器從該來源接收資料時，就會知道資料來源，例如Sensor。
title: 瞭解「截止」時間
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 瞭解「截止」時間{#understanding-as-of-time}

當Data Workbench伺服器從該來源接收資料時，就會知道資料來源，例如Sensor。

截止時間保證[!DNL data workbench server]具有其所知所有資料源的資料。

假設我們有一組三個[!DNL Sensors]，會將資料傳送至[!DNL data workbench server]:WEB1、WEB2和WEB3。 當[!DNL data workbench server]接收並處理來自這些[!DNL Sensors]的資料時，會自動產生來自這些來源的資料。 「截止時間」表示[!DNL data workbench server]上次從這三個源接收資料的時間。

實際上，[!DNL data workbench server]只關心「截止」時間，而不關心「牆時間」，或牆上時鐘的時間。 [!DNL data workbench server]只將該時間知為截止時間。 這對於報表用途尤其重要，因為它可保證報表一律以「截止時間」執行，確保系統的使用者絕不會傳送僅含有部分資料的報表。

[!DNL data workbench server]使用從傳送器傳送的資料來提供截止時間，無論是從網站收集的實際資料或您的[!DNL Sensors]所傳送的週期性心率。 這些心率有兩個用途：

1. 在[!DNL Sensor]和[!DNL data workbench server]之間保持HTTP/1.1持續連接開啟。

1. 在未收集網站流量並傳送至[!DNL data workbench server]的事件中保持「截止時間」最新。
