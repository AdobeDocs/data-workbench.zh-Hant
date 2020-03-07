---
description: Sensor的內容類型篩選功能旨在免除儲存和處理分析用途不方便的資訊的需求。
solution: Analytics
title: 依內容類型篩選
topic: Data workbench
uuid: 8a3b567b-8c7b-4ca2-bfcb-74a1addda2bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 依內容類型篩選{#filtering-by-content-type}

Sensor的內容類型篩選功能旨在免除儲存和處理分析用途不方便的資訊的需求。

許多透過網頁伺服器API提供的要求資料在商業分析中並不實用。 儲存和處理成本昂貴，而 [!DNL Sensor’s] 內容類型篩選可讓您避免不必要的儲存和處理。

為了最大化Web日誌資料處理效能並減少必須儲存的測量資料量， [!DNL Site] 獲取所有Web內容類型請求的測量資料（請求資料、日誌條目、日誌資料等），除特別列出的內容類型（如級聯樣式表、影像請求等）外，這些類型在被發送到資料工作台伺服器之前被過濾掉 [!DNL Sensor]。 對於整個Web伺服器，此篩選可以禁用，也可以通過將名稱——值對&quot;Log=1&quot;添加到特定嵌入對象的查詢字串(例如， [!DNL http://www.mysite.com/advertisement.gif?Log=1])來覆蓋特定內容對象。
