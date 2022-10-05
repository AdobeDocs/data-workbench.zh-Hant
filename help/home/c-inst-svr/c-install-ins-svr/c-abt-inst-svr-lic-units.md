---
description: Insight Server分為兩種授權類型。
title: 關於 Insight Server 授權單位
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
exl-id: 82d6fa29-d36e-480d-a975-f5a5e60a32d2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 7%

---

# 關於 Insight Server 授權單位{#about-insight-server-license-units}

{{eol}}

Insight Server分為兩種授權類型。

以下是兩種授權類型：

* [資料處理單元(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [檔案伺服器單元 (FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## 資料處理單元(DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

此類 [!DNL Insight Server] 可以處理、儲存及提供Adobe資料集的資料。 您可以選擇儲存包含資料集建構來源資料的記錄檔，或從 [!DNL Insight Server] 檔案伺服器單元(FSU)。 DPU是 [!DNL Insight Server] 與 [!DNL Insight] 和 [!DNL Report] 客戶直接互動。

如果您要安裝 [!DNL Insight Server] DPU，請參閱 [Insight Server DPU的安裝程式](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc).

## 檔案伺服器單元 (FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

此類型的伺服器配置為從一個或多個伺服器接收和儲存事件資料 [!DNL Sensor] 或事件資料復寫例項( [!DNL Repeater] 功能)，並將資料串流至一或多個 [!DNL Insight Server] 用於建立Adobe資料集的資料處理單位(DPU)。 DPU使用可最佳化事件資料傳輸至DPU的通訊協定與FSU通訊，且比維護一般檔案伺服器上的記錄檔快得多。 使用FSU還通過允許將日誌資料儲存在成本較低的儲存硬體上而降低硬體成本，並通過允許多個 [!DNL Sensors] 指向單一 [!DNL Insight Server].

如果您要安裝 [!DNL Insight Server] FSU，參見 [Insight Server FSU的安裝程式](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016).
