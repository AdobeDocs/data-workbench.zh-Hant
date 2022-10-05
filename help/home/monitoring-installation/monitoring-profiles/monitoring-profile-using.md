---
description: Data Workbench的設定檔狀態設定檔會根據設定檔，而非伺服器量度或歷史資料，提供Data Workbench伺服器運作狀況的目前資訊。
title: Data Workbench 設定檔狀態工作區
uuid: b54713c8-863d-4376-8ebf-4a2985e28c76
exl-id: 40b9b0bf-4fd9-48d8-875b-514921c520cd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 4%

---

# Data Workbench 設定檔狀態工作區{#data-workbench-profile-status-workspace}

{{eol}}

Data Workbench的設定檔狀態設定檔會根據設定檔，而非伺服器量度或歷史資料，提供Data Workbench伺服器運作狀況的目前資訊。

## Data Workbench設定檔狀態 {#section-65d1fa393cfd450cbacef3cba823fcc1}

此狀態設定檔會提供最新的Data Workbench伺服器資訊，但不是相當即時，因為代理程式每十分鐘會被輪詢一次，且報表一律會包含這10分鐘的延遲。 更準確地說，此設定檔產生的資料集可提供代理程式對伺服器的最新觀察，而代理程式的預設輪詢期通常為10分鐘。

如需Data Workbench設定檔狀態設定檔中所使用維度的其他參考資訊，請參閱 [分析設定檔狀態設定檔](../../../home/monitoring-installation/monitoring-profiles/monitoring-profile-using.md#concept-d4cd7da41c8a42bab4aea25418264e64).

![](assets/Status_General_Status.png)

此報告更適用於監控操作，而非元件或特定流量波動。

![](assets/Status_General_page.png)

這讓我們了解誰處於什麼模式：如果看到某個配置檔案的「快速輸入」速率很高，則該配置檔案處於「快速輸入」模式。

如果「已停止」量度為1，則伺服器已停止。 如果值為0，則伺服器未停頓。

**大批次載入的日誌讀取**

![](assets/Status_General_stalled_log.png)
