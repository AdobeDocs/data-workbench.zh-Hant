---
description: Sensor的內容類型篩選功能旨在消除儲存和處理不適合分析用途的資訊的需求。
title: 依內容類型篩選
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
exl-id: 0ed93a18-ef47-462b-8609-3ec98b037e6b
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 4%

---

# 依內容類型篩選{#filtering-by-content-type}

Sensor的內容類型篩選功能旨在消除儲存和處理不適合分析用途的資訊的需求。

透過網站伺服器API取得的請求資料，在業務分析中並無用處。 儲存和處理成本很高，[!DNL Sensor’s]內容類型篩選功能允許您避免不必要的儲存和處理。

為了最大化Web日誌資料處理效能並減少必須儲存的測量資料量，[!DNL Site]獲取所有Web內容類型請求的測量資料（請求資料、日誌條目、日誌資料等），但具體列出的內容類型（如級聯樣式表、影像請求等）除外，這些內容類型在通過[!DNL Sensor]將其傳輸到Data Workbench伺服器之前被過濾掉。 此篩選可針對整個Web伺服器禁用，也可以通過將名稱值對&quot;Log=1&quot;添加到特定嵌入對象的查詢字串（例如[!DNL https://www.mysite.com/advertisement.gif?Log=1]）來覆蓋特定內容對象。
