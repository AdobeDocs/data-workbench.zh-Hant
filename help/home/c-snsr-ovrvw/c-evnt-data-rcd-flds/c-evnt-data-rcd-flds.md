---
description: 記錄檔(.vsl)檔案包含事件資料欄位，這些欄位是由Sensor從伺服器收集，由Data Workbench伺服器在資料集建構程式中使用。
title: 事件資料記錄欄位（.vsl檔案）
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 2%

---

# 事件資料記錄欄位{#event-data-record-fields}

{{eol}}

記錄檔(.vsl)檔案包含事件資料欄位，這些欄位是由Sensor從伺服器收集，由Data Workbench伺服器在資料集建構程式中使用。

欄位名稱通常會遵循W3C擴充記錄檔格式的命名慣例。 許多欄位的前置詞都表示欄位中包含的資訊的來源：

* &quot;cs&quot;表示從客戶端到伺服器的通信
* &quot;sc&quot;表示從伺服器到客戶端的通信
* &quot;s&quot;表示來自伺服器的資訊
* &quot;c&quot;表示來自客戶端的資訊
* &quot;x&quot;表示由Adobe產品建立的資訊
