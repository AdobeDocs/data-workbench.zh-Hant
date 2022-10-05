---
description: 本檔案說明設定檔，以及Data Workbench監控設定檔所採用的欄位、維度和量度。
title: Data Workbench 設定檔維度與量度
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Data Workbench 設定檔維度與量度{#data-workbench-profile-dimensions-and-metrics}

{{eol}}

本檔案說明設定檔，以及Data Workbench監控設定檔所採用的欄位、維度和量度。

若要監控Data Workbench伺服器，資料會使用指令碼來收集，此指令碼會剖析「詳細狀態」，同時擷取特定伺服器資訊。 接著，Data Workbench伺服器資訊會傳遞至Data Workbench Sensor的頁面標籤呼叫，以收集並儲存至VSL檔案。

## Data Workbench監控設定檔所採用的設定檔 {#section-b5b1234f55c3407dae8e68b031b7cd7f}

這些設定檔提供的維度和量度可讓您檢視伺服器狀態和效能資料：

* [Dimension（位於分析設定檔狀態設定檔中）](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimension（位於Insight Server狀態設定檔中）](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimension在Insight歷史設定檔中](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [分析歷史監控設定檔中的量度](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

狀態設定檔可讓您從操作角度查看Data Workbench目前的執行情形。 此 **設定檔狀態** 設定檔與 **伺服器狀態** 設定檔會從「詳細狀態」和data workbench伺服器收集資料。 所有收集的資料都會放入 `cs-uri-query` 欄位供使用。

此 **歷史設定檔** 允許您使用歷史資料評估配置和硬體更改的影響。 歷史配置檔案可能最有用，因為它允許您評估配置和硬體更改在一段時間內的影響。
