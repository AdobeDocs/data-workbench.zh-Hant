---
description: Sensor可免除傳統上從事資料收集的大量人力，讓您從網際網路通道自動取得資料。
solution: Analytics
title: 資料收集程序如何運作？
uuid: d34e5938-217b-4a1e-b96e-55a02b1c3af0
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---


# 資料收集程序如何運作？{#how-does-the-data-collection-process-work}

Sensor可免除傳統上從事資料收集的大量人力，讓您從網際網路通道自動取得資料。

在許多情況下，使用可 [!DNL Sensor] 以大大簡化您的資料管理流程。

現今大型的網際網路、外部網路和內部網路網站，通常都可在一系列的Web伺服器上執行。 產生的記錄檔和資料可能會非常龐大，而且管理起來十分麻煩。 例如，若您的網站執行30部Web伺服器，通常您的某位員工（或外包服務供應商的員工）會提取並合併30部伺服器上的每個記錄檔，然後對其執行報表。 在每 [!DNL Sensor] 台Web伺服器上安裝會自動化整個程式，降低開支並即時提供資料。

若要自動化此程式， [!DNL Sensor] 請直接從每個網站伺服器收集網站上流量的原始資訊。 擷取的原始資 [!DNL Sensor] 料稱為事件資料，與您的Web伺服器記錄在其記錄檔中的資料類型類似。

若要擷取此資料，Web伺服器 [!DNL Sensor] 處理的每個HTTP要求都會記錄相關資訊。 [!DNL Sensor] 然後緩衝資訊以防止網路故障，並通過HTTP/S安全地將資訊傳輸到您指 [!DNL data workbench server] 定的位置。

在收到 [!DNL data workbench server] 資料後，它會以高度壓縮的格式檔案處理並儲存您的記錄檔，讓您輕鬆在價格不昂貴的硬體上 [!DNL .vsl] 維護大量資料。

如需檔案中所收集之事件資料欄位的 [!DNL Sensor] 詳細 [!DNL .vsl] 資訊，請 [參閱事件資料記錄欄位](../../home/c-snsr-ovrvw/c-evnt-data-rcd-flds/c-evnt-data-rcd-flds.md#concept-ed2a8797cb5b4995b55ffd50a9f12a44)。
