---
description: Sensor通過消除傳統上涉及資料收集的大量人力，自動從您的Internet通道獲取資料。
title: 資料收集程序如何運作？
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# 資料收集程序如何運作？{#how-does-the-data-collection-process-work}

Sensor通過消除傳統上涉及資料收集的大量人力，自動從您的Internet通道獲取資料。

在許多情況下，使用[!DNL Sensor]可以大大簡化資料管理過程。

當今的大型網際網路、外聯網和內聯網站點通常在一系列Web伺服器上運行。 產生的記錄檔和資料可能非常龐大且難以管理。 例如，如果您的網站運行30台Web伺服器，通常您的一名員工（或外包服務提供商的員工）將提取並整合30台伺服器上的每個日誌檔案，然後對這些伺服器運行報告。 在每個Web伺服器上安裝[!DNL Sensor]會自動化整個流程，從而減少開支，並使資料可以即時提供。

為了自動執行此過程，[!DNL Sensor]直接從每個Web伺服器收集有關網站上流量的原始資訊。 [!DNL Sensor]擷取的原始資料稱為事件資料，與您的網站伺服器在其記錄檔中記錄的資料類型類似。

要捕獲此資料，[!DNL Sensor]內的檢測記錄有關Web伺服器處理的每個HTTP請求的資訊。 [!DNL Sensor] 然後緩衝資訊以防止網路故障，並通過HTTP/S安全地將資訊傳輸到您指 [!DNL data workbench server] 定的資訊。

[!DNL data workbench server]收到資料後，它會以高度壓縮的[!DNL .vsl]格式檔案處理和儲存日誌檔案，讓您能夠輕鬆地在便宜的硬體上維護大量資料。

有關[!DNL .vsl]檔案中[!DNL Sensor]收集的事件資料欄位的資訊，請參閱[事件資料記錄欄位](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。
