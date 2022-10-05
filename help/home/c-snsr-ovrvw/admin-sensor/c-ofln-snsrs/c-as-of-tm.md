---
description: 當Data Workbench伺服器從該來源接收資料時，就會知道資料來源，例如Sensor。
title: 瞭解「截止」時間
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
exl-id: 58ea5c6f-de6b-48d2-b573-f265857026da
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# 瞭解「截止」時間{#understanding-as-of-time}

{{eol}}

當Data Workbench伺服器從該來源接收資料時，就會知道資料來源，例如Sensor。

「截止時間」保證 [!DNL data workbench server] 有其所知資料來源的資料。

假設我們有三組 [!DNL Sensors] 將資料傳送至 [!DNL data workbench server]:WEB1、WEB2和WEB3。 作為 [!DNL data workbench server] 從這些 [!DNL Sensors]，就會自動從這些來源取得資料。 「截止時間」表示 [!DNL data workbench server] 從這三個來源收到資料。

實際上， [!DNL data workbench server] 只關心「截止時間」，而不關心「牆時間」，或牆上的時鐘。 此 [!DNL data workbench server] 只知道時間作為截止時間。 這對於報表用途尤其重要，因為它可保證報表一律以「截止時間」執行，確保系統的使用者絕不會傳送僅含有部分資料的報表。

此 [!DNL data workbench server] 使用從傳送器傳送的資料來提供截止時間，無論是從網站收集的實際資料或您所傳送的定期心率 [!DNL Sensors]. 這些心率有兩個用途：

1. 若要在 [!DNL Sensor] 和 [!DNL data workbench server].

1. 在未收集網站流量並傳送至的事件中，讓「截止時間」保持最新 [!DNL data workbench server].
