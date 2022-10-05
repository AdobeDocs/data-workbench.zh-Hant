---
description: Sensor的內容類型篩選功能旨在消除儲存和處理不適合分析用途的資訊的需求。
title: 依內容類型篩選
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# 依內容類型篩選{#filtering-by-content-type}

{{eol}}

Sensor的內容類型篩選功能旨在消除儲存和處理不適合分析用途的資訊的需求。

透過網站伺服器API取得的請求資料，在業務分析中並無用處。 儲存和處理成本高， [!DNL Sensor’s] 內容類型篩選可讓您避免不必要的儲存和處理。

為了最大化網站記錄檔資料處理效能並減少必須儲存的測量資料量， [!DNL Site] 取得所有網路內容類型請求的測量資料（請求資料、記錄項目、記錄資料等），但特別列出的內容類型（例如階層式樣式表、影像請求等）除外，這些類型在透過資料工作台伺服器傳送至資料工作台伺服器之前，會先經過篩選 [!DNL Sensor]. 此篩選可針對整個Web伺服器而停用，也可針對特定內容物件將名稱值組&quot;Log=1&quot;新增至特定內嵌物件的查詢字串，以覆寫該篩選(例如， [!DNL https://www.mysite.com/advertisement.gif?Log=1])。
