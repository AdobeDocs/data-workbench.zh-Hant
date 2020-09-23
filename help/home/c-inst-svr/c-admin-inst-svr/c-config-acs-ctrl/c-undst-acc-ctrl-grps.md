---
description: 有5個預先建立的存取控制群組可供使用，但您可以視需要建立和管理其他群組。
solution: Analytics
title: 瞭解存取控制群組
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---


# 瞭解存取控制群組{#understanding-access-control-groups}

有5個預先建立的存取控制群組可供使用，但您可以視需要建立和管理其他群組。

您可以定義每個訪問控制組的成員以及每個組具有只讀或讀寫訪問權限的目錄。

預先定義的群組定義如下：

| 群組 | 說明 |
|---|---|
| 管理員 | 允許訪問所有目錄和檔案。 預設IP地址為127.0.0.1（本地主機）。 |
| 感測器 | 僅允許訪問用於傳輸資料的 [!DNL Sensor] 檔案。 |
| 使用者 | 允許對用戶執行基本分析任務所需 [!DNL Insight] 的元素進行只讀訪問。 |
| 超級用戶 | 允許對用戶執行基本分析任務所需元素的只讀 [!DNL Insight] 訪問，以及對資料夾的讀和寫訪問，以 [!DNL Profiles] 修改配置檔案。 |
| 群集伺服器 | 允許訪問指 [!DNL Insight Servers] 定為群集伺服器的伺服器。 |
| 報表伺服器 | 允許訪問 [!DNL Report] 連接到的電腦 [!DNL Insight Server]。 |

訪問控制組的成員使用其IP地址或SSL證書資訊定義。

如果SSL憑證不可用，則可使用IP位址來定義群組成員。 通常的安裝 [!DNL Insight] 包含SSL憑證，而憑證的使用則 [!DNL Sensor(s)] 為選擇性。 對於 [!DNL Insight Server]，群集伺服器是使用IP位址而非SSL憑證來定義。

以下代碼可用於定義組成員：

| 存取類型代碼 | 定義 |
|---|---|
| O | 組織 |
| CN | 通用名稱 |
| L | 位置 |
| ST | 州或省 |
| C | 國家/地區 |
| OU | 組織單位 |
| 電子郵件 | 電子郵件地址 |

