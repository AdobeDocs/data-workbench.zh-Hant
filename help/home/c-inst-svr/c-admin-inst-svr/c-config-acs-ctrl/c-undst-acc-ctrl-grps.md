---
description: 有五個預先建立的訪問控制組可用，但您可以根據需要建立和管理其他組。
title: 瞭解存取控制群組
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---

# 瞭解存取控制群組{#understanding-access-control-groups}

{{eol}}

有五個預先建立的訪問控制組可用，但您可以根據需要建立和管理其他組。

您可以定義每個訪問控制組的成員以及每個組具有只讀或讀寫訪問權限的目錄。

預先定義的群組定義如下：

| 群組 | 說明 |
|---|---|
| 管理員 | 允許訪問所有目錄和檔案。 預設IP地址為127.0.0.1（本地主機）。 |
| 感測器 | 僅允許訪問 [!DNL Sensor] 傳輸資料。 |
| 用戶 | 允許唯讀存取 [!DNL Insight] 執行基本分析任務的用戶。 |
| 超級用戶 | 允許唯讀存取 [!DNL Insight] 執行基本分析任務的用戶，以及對 [!DNL Profiles] 用於修改配置檔案的資料夾。 |
| 群集伺服器 | 允許存取 [!DNL Insight Servers] 指定為群集伺服器。 |
| 報表伺服器 | 允許存取 [!DNL Report] 連接到的電腦 [!DNL Insight Server]. |

使用其IP位址或SSL憑證資訊來定義存取控制群組的成員。

如果SSL憑證無法使用，則可使用IP位址來定義群組成員。 典型安裝 [!DNL Insight] 包含SSL憑證，而使用憑證 [!DNL Sensor(s)] 為選用。 針對 [!DNL Insight Server]，則會使用IP位址來定義叢集伺服器，而非使用SSL憑證。

可使用下列程式碼來定義群組成員：

| 存取類型程式碼 | 定義 |
|---|---|
| O | 組織 |
| CN | 公用名稱 |
| L | 位置 |
| ST | 州或省 |
| C | 國家/地區 |
| 歐 | 組織單位 |
| 電子郵件 | 電子郵件地址 |
