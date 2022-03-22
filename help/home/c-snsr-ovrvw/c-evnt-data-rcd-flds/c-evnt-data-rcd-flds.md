---
description: 日誌(.vsl)檔案包含事件資料欄位，這些欄位由感測器從伺服器收集，資料工作台伺服器在資料集構建過程中使用。
title: 事件資料記錄欄位（.vsl檔案）
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 2%

---

# 事件資料記錄欄位{#event-data-record-fields}

日誌(.vsl)檔案包含事件資料欄位，這些欄位由感測器從伺服器收集，資料工作台伺服器在資料集構建過程中使用。

欄位名稱通常遵循W3C擴展日誌檔案格式的命名約定。 許多欄位都具有前置詞，表示該欄位中包含的資訊的來源：

* 「cs」表示從客戶端到伺服器的通信
* 「sc」表示從伺服器到客戶端的通信
* 「s」表示來自伺服器的資訊
* 「c」表示來自客戶端的資訊
* 「x」表示由Adobe產品建立的資訊
