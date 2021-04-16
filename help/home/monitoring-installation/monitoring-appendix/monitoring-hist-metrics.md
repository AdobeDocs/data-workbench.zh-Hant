---
description: 以下列出資料工作台歷史監控設定檔中包含的量度，以及其衍生方式。
title: Data Workbench 歷史監控設定檔中的量度
uuid: 47b874f7-8acb-4593-9ac9-5997d5279e52
exl-id: 65f0f605-f128-45bb-8f6c-95284b2da740
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 2%

---

# Data Workbench 歷史監控設定檔中的量度{#metrics-in-the-data-workbench-historical-monitoring-profile}

以下列出資料工作台歷史監控設定檔中包含的量度，以及其衍生方式。

| **提醒關鍵產業** | 每個Ping的「緊急警報」維度的總和。 |
|---|---|
| **警報關閉** | 每個Ping的「向下警報」維度的總和。 |
| **警報警告** | 每個Ping的「警報警告」維度的總和。 |
| **所有元件** | 元件檢查成功等於&quot;1&quot;的Ping計數除以Ping度量乘以100。 |
| **截止延遲分鐘** | 此度量是每個Ping的「截止延遲分鐘數」的總和，再除以「Ping」度量。 |
| **塊** | 每個區塊的1之和。 |
| **全部封鎖** | 所有區塊。 |
| **整體容量** | 容量大小度量乘以2加容量行度量，除以3。 |
| **容量行** | 每個Ping的「容量行百分比」維除以Ping度量的總和。 |
| **容量大小** | 每個Ping的「容量大小百分比」維的總和，除以Ping度量。 |
| **通訊** | 快速檢查成功符合&quot;1&quot;的Ping數，除以Ping度量。 |
| **詳細檢查秒數** | Ping類型為「伺服器」的每個Ping的「詳細檢查秒數」維的總和，除以Ping度量。 |
| **DimensionGigaBytes** | 每個Ping的DimensionGB總和，除以Ping度量。 |
| **磁碟&quot;x&quot;** | 磁碟度量的計算方法是：將每個Ping的磁碟使用百分比的總和除以Ping度量。 |
| **估計掃描分鐘數** | 這是每個Ping的「估計掃描秒數」除以「估計掃描秒數」大於零的「Ping」度量（全部除以6）的總和。 |
| **每分鐘快速輸入MB** | 每個Ping的快速輸入MegaBytes/Minute的總和除以Ping數（當快速輸入MegaBytes/Minute大於零時）。 |
| **快速輸入模式** | 其中「處理模式」維度等於「快速輸入」除以Ping。 |
| **每分鐘快速合併MegaBytes** | 每個Ping的快速合併兆位元組／分鐘總和，除以Ping度量。 |
| **快速合併模式** | 處理模式等於「快速合併」除以Ping度量的Ping。 |
| **欄位千兆位元組** | 每個Ping的欄位Gigb維除以Ping度量的總和。 |
| **載入** | 每個Ping的「平均負載」維的總和，除以「Ping」度量。 |
| **日誌讀取** | 每個Ping的「日誌讀取處理」維度的總和，除以Ping度量，全部除以10。 |
| **「記憶體」頁** | 每個Ping的「記憶體頁檔案百分比」總和除以Ping度量。 |
| **物理記憶體** | 每個Ping的「記憶體物理百分比」維的總和，除以Ping度量。 |
| **記憶體查詢** | 每個Ping的「記憶體查詢百分比」總和除以Ping度量。 |
| **總記憶體GB** | 每個Ping的「記憶體物理MegaBytes總」維的總和，除以Ping度量。 |
| **網路連接** | 這是每個Ping的網路連接總和除以Ping度量。 |
| **Ping通X總容量** | Ping度量乘以總容量度量。 |
| **輪詢延遲毫秒** | 每個Ping的「輪詢延遲不等於秒」維度的總和，除以Ping度量，全部乘以10。 |
| **查詢運行** | 估計掃描秒數大於&quot;0&quot;的每個Ping的總和，除以Ping類型等於&quot;server&quot;的Ping度量。 |
| **快速檢查秒數** | Ping類型等於「伺服器」的每個Ping的快速檢查秒數總和，除以Ping度量。 |
| **輸出行** | 每個ping的「輸出行」維的總和除以Ping度量，再乘以100000。 |
| **即時模式** | 處理模式維度等於「即時」的Ping數除以Ping度量，全部乘以100。 |
| **重新處理模式** | 100減去處理模式等於「即時」的Ping數除以Ping度量，再乘以100。 |
| **已停止** | 分析[描述檔狀態](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)描述檔中的處理停止維度總和。 |
| **臨時資料庫** | 每個Ping的臨時資料庫空間百分比之和除以Ping度量。 |
| **轉換** | 每個Ping的轉換百分比除以Ping度量的總和再除以10。 |
