---
description: Insight Server提供兩種授權類型。
title: 關於 Insight Server 授權單位
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# 關於 Insight Server 授權單位{#about-insight-server-license-units}

Insight Server提供兩種授權類型。

以下是兩種授權類型：

* [資料處理單元(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [檔案伺服器單元 (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## 資料處理單元(DPU){#section-bf589e13cf5c43a58f8f85a457de6f65}

此類型的[!DNL Insight Server]可處理、儲存和提供來自Adobe資料集的資料。 它可以選擇儲存包含構建資料集的源資料的日誌檔案，也可以從[!DNL Insight Server]檔案伺服器單元(FSU)接收該資料。 DPU是[!DNL Insight]和[!DNL Report]客戶端直接與之交互的[!DNL Insight Server]類型。

如果要安裝[!DNL Insight Server] DPU，請參閱[ Installation Procedures for an Insight Server DPU](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)。

## 檔案伺服器單元 (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

這種類型的伺服器被配置為從一個或多個[!DNL Sensor]或事件資料複製實例（具有特殊使用許可證的[!DNL Repeater]功能）接收和儲存事件資料，並將資料流到一個或多個[!DNL Insight Server]資料處理單元(DPU)，以構建Adobe資料集。 DPU使用協定與FSU通信，該協定優化了事件資料到DPU的傳輸，並且比維護普通檔案伺服器上的日誌檔案要快得多。 使用FSU還通過允許將日誌資料儲存在成本較低的儲存硬體上來降低硬體成本，並通過允許多個[!DNL Sensors]指向單個[!DNL Insight Server]來降低管理複雜性。

如果要安裝[!DNL Insight Server] FSU，請參閱[ Installation Procedures for an Insight Server FSU](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。
