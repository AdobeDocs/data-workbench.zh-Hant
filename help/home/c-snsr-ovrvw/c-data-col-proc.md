---
description: Sensor通過消除傳統上涉及資料收集的大量人力，自動從您的Internet通道獲取資料。
title: 資料收集程序如何運作？
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# 資料收集程序如何運作？{#how-does-the-data-collection-process-work}

{{eol}}

Sensor通過消除傳統上涉及資料收集的大量人力，自動從您的Internet通道獲取資料。

在許多情況下，使用 [!DNL Sensor] 可大幅簡化資料管理流程。

當今的大型網際網路、外聯網和內聯網站點通常在一系列Web伺服器上運行。 產生的記錄檔和資料可能非常龐大且難以管理。 例如，如果您的網站運行30台Web伺服器，通常您的一名員工（或外包服務提供商的員工）將提取並整合30台伺服器上的每個日誌檔案，然後對這些伺服器運行報告。 安裝 [!DNL Sensor] 每個web伺服器都會自動執行整個流程，從而減少開支，使資料可以即時提供。

要自動執行此過程， [!DNL Sensor] 直接從每個網站伺服器收集網站上流量的原始資訊。 原始資料 [!DNL Sensor] 「捕獲」稱為事件資料，類似於您的Web伺服器在其日誌檔案中記錄的資料類型。

要捕獲此資料，請在 [!DNL Sensor] 記錄您的Web伺服器處理之每個HTTP要求的相關資訊。 [!DNL Sensor] 然後緩衝資訊以防止網路故障，並通過HTTP/S安全地將資訊傳輸到 [!DNL data workbench server] 指定的。

在 [!DNL data workbench server] 接收資料，它會處理並儲存高度壓縮的記錄檔 [!DNL .vsl] 格式化檔案，讓您輕鬆在便宜的硬體上維護大量資料。

如需所收集事件資料欄位的相關資訊，請參閱 [!DNL Sensor] in [!DNL .vsl] 檔案，請參閱 [事件資料記錄欄位](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44).
