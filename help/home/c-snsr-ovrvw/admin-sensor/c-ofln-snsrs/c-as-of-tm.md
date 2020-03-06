---
description: 當資料工作台伺服器從該源接收資料時，它會感知到資料源，如感測器。
solution: Insight
title: 瞭解「截止」時間
uuid: a1853573-e77c-41f7-8b99-2843e38cc82d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 瞭解「截止」時間{#understanding-as-of-time}

當資料工作台伺服器從該源接收資料時，它會感知到資料源，如感測器。

「截止時間」是保證資料 [!DNL data workbench server] 具有其所知所有資料來源的資料。

假設我們有三套可傳送資 [!DNL Sensors] 料至的資料 [!DNL data workbench server]:WEB1、WEB2和WEB3。 當從這 [!DNL data workbench server] 些來源接收並處理資料時 [!DNL Sensors]，就會自動預期來自這些來源的資料。 截止時間表示上次從這三個來 [!DNL data workbench server] 源接收資料的時間。

實際上，他 [!DNL data workbench server] 們只關心「截止時間」，而不關心「牆時間」，也不關心牆上的時鐘。 這 [!DNL data workbench server] 個時間只是As Of Time。 這對於報告而言尤其重要，因為它保證報告始終根據截止時間運行，這可確保只包含部分資料的報告永遠不能發送給系統的最終用戶。

此 [!DNL data workbench server] 變數會使用從傳送器傳送的資料來提供截止時間，不論是從網站收集的實際資料或您傳送的定期心率 [!DNL Sensors]。 這些心率有兩個用途：

1. 若要在和之間保持HTTP/1.1持續連 [!DNL Sensor] 接開啟 [!DNL data workbench server]。

1. 若要在未收集網站流量並傳送至的情況下，保持「截止時間」為最新 [!DNL data workbench server]。

