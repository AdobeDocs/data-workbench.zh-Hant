---
description: 本檔案說明設定檔，以及Data Workbench監控設定檔所採用的欄位、維度和量度。
title: Data Workbench 設定檔維度與量度
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
exl-id: cfad9897-2ea3-47e4-aa36-416e0fde9358
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 5%

---

# Data Workbench 設定檔維度與量度{#data-workbench-profile-dimensions-and-metrics}

本檔案說明設定檔，以及Data Workbench監控設定檔所採用的欄位、維度和量度。

若要監控Data Workbench伺服器，資料會使用指令碼來收集，此指令碼會剖析「詳細狀態」，同時擷取特定伺服器資訊。 接著，Data Workbench伺服器資訊會傳遞至Data Workbench Sensor的頁面標籤呼叫，以收集並儲存至VSL檔案。

## Data Workbench監控配置檔案{#section-b5b1234f55c3407dae8e68b031b7cd7f}所採用的配置檔案

這些設定檔提供的維度和量度可讓您檢視伺服器狀態和效能資料：

* [Dimension（位於分析設定檔狀態設定檔中）](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Dimension（位於Insight Server狀態設定檔中）](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [Dimension在Insight歷史設定檔中](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [分析歷史監控設定檔中的量度](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

狀態設定檔可讓您從操作角度查看Data Workbench目前的執行情形。 **設定檔狀態**&#x200B;設定檔和&#x200B;**伺服器狀態**&#x200B;設定檔會從詳細狀態和Data Workbench伺服器收集資料。 所有收集的資料都放入`cs-uri-query`欄位中供使用。

**歷史配置檔案**&#x200B;允許您使用歷史資料評估配置和硬體更改的影響。 歷史配置檔案可能最有用，因為它允許您評估配置和硬體更改在一段時間內的影響。
