---
description: Sensor可免除傳統上從事資料收集的大量人力，讓您從網際網路通道自動取得資料。
title: 資料收集程序如何運作？
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
exl-id: dd930739-ca24-4166-8ebd-84b65f6f3754
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# 資料收集程序如何運作？{#how-does-the-data-collection-process-work}

Sensor可免除傳統上從事資料收集的大量人力，讓您從網際網路通道自動取得資料。

在許多情況下，使用[!DNL Sensor]可大幅簡化您的資料管理程式。

現今大型的網際網路、外部網路和內部網路網站，通常都可在一系列的Web伺服器上執行。 產生的記錄檔和資料可能會非常龐大，而且管理起來十分麻煩。 例如，若您的網站執行30部Web伺服器，通常您的某位員工（或外包服務供應商的員工）會提取並合併30部伺服器上的每個記錄檔，然後對其執行報表。 在每台Web伺服器上安裝[!DNL Sensor]會自動完成整個過程，從而減少開支並即時提供資料。

為自動化此程式，[!DNL Sensor]會直接從每個Web伺服器收集網站上流量的原始資訊。 [!DNL Sensor]擷取的原始資料稱為事件資料，與您的Web伺服器在其記錄檔中記錄的資料類型類似。

要捕獲此資料，[!DNL Sensor]中的工具記錄有關Web伺服器處理的每個HTTP請求的資訊。 [!DNL Sensor] 然後緩衝資訊以防止網路故障，並通過HTTP/S安全地將資訊傳輸到 [!DNL data workbench server] 您指定的。

在[!DNL data workbench server]收到資料後，它會以高度壓縮的[!DNL .vsl]格式檔案處理並儲存您的記錄檔，讓您輕鬆在便宜的硬體上維護大量資料。

有關[!DNL .vsl]檔案中[!DNL Sensor]收集的事件資料欄位的資訊，請參閱[事件資料記錄欄位](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。
