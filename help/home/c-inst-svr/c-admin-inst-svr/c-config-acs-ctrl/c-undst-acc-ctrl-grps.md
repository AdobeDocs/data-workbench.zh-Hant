---
description: 有五個預先建立的訪問控制組可用，但您可以根據需要建立和管理其他組。
title: 瞭解存取控制群組
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---

# 瞭解存取控制群組{#understanding-access-control-groups}

有五個預先建立的訪問控制組可用，但您可以根據需要建立和管理其他組。

您可以定義每個訪問控制組的成員以及每個組具有只讀或讀寫訪問權限的目錄。

預先定義的群組定義如下：

| 群組 | 說明 |
|---|---|
| 管理員 | 允許訪問所有目錄和檔案。 預設IP地址為127.0.0.1（本地主機）。 |
| 感測器 | 僅允許訪問[!DNL Sensor]用於傳輸資料的檔案。 |
| 使用者 | 允許對[!DNL Insight]用戶執行基本分析任務所需的元素進行只讀訪問。 |
| 超級用戶 | 允許對[!DNL Insight]用戶執行基本分析任務所需的元素進行只讀訪問，並允許對[!DNL Profiles]資料夾進行讀寫訪問以修改配置檔案。 |
| 群集伺服器 | 允許訪問指定為群集伺服器的[!DNL Insight Servers]。 |
| 報表伺服器 | 允許訪問連接到[!DNL Insight Server]的[!DNL Report]電腦。 |

使用其IP位址或SSL憑證資訊來定義存取控制群組的成員。

如果SSL憑證無法使用，則可使用IP位址來定義群組成員。 典型的[!DNL Insight]安裝包含SSL憑證，而對[!DNL Sensor(s)]使用憑證則為選用。 對於[!DNL Insight Server]，群集伺服器是使用IP地址而非SSL證書來定義的。

可使用下列程式碼來定義群組成員：

| 存取類型程式碼 | 定義 |
|---|---|
| O | 組織 |
| CN | 公用名稱 |
| L | 位置 |
| ST | 州或省 |
| C | 國家/地區 |
| 歐 | 組織單位 |
| 電子郵件 | 電子郵件 地址 |
