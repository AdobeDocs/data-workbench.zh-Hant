---
description: 資料工作台描述檔狀態描述檔會根據描述檔提供資料工作台伺服器狀況的目前資訊，而非伺服器度量或歷史資料。
title: Data Workbench 設定檔狀態工作區
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Data Workbench 設定檔狀態工作區{#data-workbench-profile-status-workspace}

資料工作台描述檔狀態描述檔會根據描述檔提供資料工作台伺服器狀況的目前資訊，而非伺服器度量或歷史資料。

## Data Workbench配置檔案狀態{#section-65d1fa393cfd450cbacef3cba823fcc1}

此狀態設定檔提供目前但不是相當即時的資料工作台伺服器資訊，因為代理每10分鐘輪詢一次，而報告一律包含這10分鐘的延遲。 更精確地說，此設定檔產生的資料集提供代理對伺服器的最新觀察，而代理的預設輪詢週期通常為10分鐘。

如需資料工作台「描述檔狀態」描述檔中使用之維度的其他參考資訊，請參閱[Insight Profile Status描述檔](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64)。

![](assets/Status_General_Status.png)

此報告更適用於監控作業，而非元件或特定流量波動。

![](assets/Status_General_page.png)

這讓我們瞭解哪些人處於何種模式：如果我們看到某個描述檔的「快速輸入」速率較高，則該描述檔會處於「快速輸入」模式。

如果「停止」量度為1，則伺服器會停止。 如果值為0，則伺服器不會停止。

**大批次載入的日誌讀取**

![](assets/Status_General_stalled_log.png)
