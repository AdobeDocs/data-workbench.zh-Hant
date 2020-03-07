---
description: 本檔案說明描述檔及其資料工作台監控描述檔所採用的欄位、維度和量度。
solution: Analytics
title: 資料工作台描述檔維度與量度
topic: Data workbench
uuid: 42ef154f-fd8b-4609-8685-96d9dbf32a3d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 資料工作台描述檔維度與量度{#data-workbench-profile-dimensions-and-metrics}

本檔案說明描述檔及其資料工作台監控描述檔所採用的欄位、維度和量度。

若要監控資料工作台伺服器，會使用指令碼來收集資料，此指令碼會分析「詳細狀態」並擷取特定伺服器資訊。 然後資料工作台伺服器資訊會傳遞至頁面標籤呼叫，讓資料工作台感測器收集並儲存至VSL檔案。

## 資料工作台監控配置檔案採用的配置檔案 {#section-b5b1234f55c3407dae8e68b031b7cd7f}

這些設定檔提供維度和量度，可讓您檢視伺服器狀態和效能資料：

* [Insight Profile Status設定檔中的維度](../../../home/monitoring-installation/monitoring-appendix/monitoring-profile-status.md#concept-d4cd7da41c8a42bab4aea25418264e64)
* [Insight Server狀態設定檔中的維度](../../../home/monitoring-installation/monitoring-appendix/monitoring-servers-profile.md#concept-8cbeb91e99bc42e2b52b22d551423f8a)
* [分析歷史資料中的維度](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)
* [前瞻分析歷史監控設定檔中的量度](../../../home/monitoring-installation/monitoring-appendix/monitoring-hist-metrics.md#concept-8fece88b1f014637bbc7c8372ee93203)

「狀態」設定檔可讓您從營運角度瞭解資料工作台目前的執行情形。 Profile Status **(配** 置檔案狀態 **** )配置檔案和Server Status（伺服器狀態）配置檔案從Detailed Status（詳細狀態）和Data Workbench（資料工作台）伺服器收集資料。 所有收集的資料都會放入欄 `cs-uri-query` 位中供使用。

歷史 **配置檔案** ，允許您使用歷史資料評估配置和硬體更改的影響。 歷史配置檔案可能最有用，因為它允許您評估配置和硬體更改隨時間變化的影響。
