---
description: 下表列出Data Workbench歷史監控設定檔中包含的量度，以及其衍生方式。
title: Data Workbench 歷史監控設定檔中的量度
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Data Workbench 歷史監控設定檔中的量度{#metrics-in-the-data-workbench-historical-monitoring-profile}

下表列出Data Workbench歷史監控設定檔中包含的量度，以及其衍生方式。

| **警報條件** | 每個Ping的「警報關鍵」維的總和。 |
|---|---|
| **警報下限** | 每個Ping的「向下警報」維度的總和。 |
| **警報警告** | 每個Ping的「警報警告」維度的總和。 |
| **所有元件** | 元件檢查成功等於「1」時的Ping計數除以Ping量度乘以100。 |
| **截止延遲分鐘數** | 此量度是每個Ping的「截止延遲分鐘數」的總和，然後除以「Ping」量度。 |
| **區塊** | 每個區塊的總和。 |
| **全部封鎖** | 所有區塊。 |
| **總容量** | 容量大小度量乘以2加上容量行度量，除以3。 |
| **容量行** | 每個Ping的「容量行百分比」維度的總和除以「Ping」度量。 |
| **容量大小** | 每個Ping的「容量大小百分比」維的總和，除以Ping度量。 |
| **通訊** | 快速檢查成功符合「1」的Ping數，除以Ping量度。 |
| **詳細檢查秒數** | 每個Ping的「詳細檢查秒數」維度的總和，其中Ping類型為「伺服器」，除以Ping量度。 |
| **DimensionGigaBytes** | 每個Ping的DimensionGB總和，除以Ping度量。 |
| **磁碟&quot;x&quot;** | 磁碟度量的計算方式是取每個Ping的磁碟使用百分比之和除以Ping度量。 |
| **估計掃描分鐘數** | 這是每個Ping的「估計掃描秒數」的總和，除以「估計掃描秒數大於零的Ping量度，全部除以6。 |
| **每分鐘快速輸入MB** | 當每分鐘快速輸入MegaBytes大於零時，每個Ping的快速輸入MegaBytes/Minute的總和除以Ping的數量。 |
| **快速輸入模式** | 處理模式維度等於「快速輸入」除以Ping的Ping。 |
| **每分鐘快速合併MegaBytes** | 每個Ping的每分鐘快速合併MB總和，除以Ping度量。 |
| **快速合併模式** | 處理模式等於「快速合併」除以Ping量度的Ping。 |
| **欄位GigaBytes** | 每個Ping的欄位GB維度總和除以Ping度量。 |
| **載入** | 每個Ping的「負載平均」維度總和，除以「Ping」量度。 |
| **日誌讀取** | 每個Ping的「記錄讀取處理」維度總和，除以「Ping」量度，全部除以10。 |
| **記憶體頁** | 每個Ping的記憶體頁面檔案百分比總和除以Ping量度。 |
| **記憶體物理** | 每個Ping的記憶體物理百分比維的總和，除以Ping度量。 |
| **記憶體查詢** | 每個Ping的記憶體查詢百分比的總和，除以Ping度量。 |
| **記憶體總GB** | 每個Ping的記憶體物理MegaBytes總維的總和，除以Ping度量。 |
| **網路連接** | 這是每個Ping的網路連接總和除以Ping度量。 |
| **整體Ping X容量** | Ping量度乘以總容量量度。 |
| **輪詢延遲毫秒** | 每個Ping的「民調問答延遲百分秒」維度總和，除以「Ping」量度，再加10。 |
| **查詢正在運行** | 每個Ping的總和，其中估計掃描秒數大於「0」，除以Ping類型等於「伺服器」的Ping度量。 |
| **快速檢查秒數** | Ping類型等於「伺服器」的每個Ping的快速檢查秒數總和，除以Ping量度。 |
| **輸出行** | 每個Ping的「輸出行」維度總和除以「Ping」量度，再乘以100000。 |
| **即時模式** | 「處理模式」維度等於「即時」的Ping數，除以「Ping」量度，再加100。 |
| **重新處理模式** | 100減去處理模式等於「即時」除以Ping量度再乘以100的Ping數。 |
| **已停止** | 分析[設定檔狀態](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)設定檔中的處理中止維度的總和。 |
| **臨時DB** | 每個Ping的臨時資料庫空間百分比總和，除以Ping度量。 |
| **轉換** | 每個Ping的轉換百分比除以Ping量度的總和除以10。 |
