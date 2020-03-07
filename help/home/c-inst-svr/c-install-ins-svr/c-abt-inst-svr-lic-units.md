---
description: Insight Server提供兩種授權類型。
solution: Insight
title: 關於Insight Server授權單位
uuid: e6a48b00-4dc1-416c-9039-01c01b86abbf
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關於Insight Server授權單位{#about-insight-server-license-units}

Insight Server提供兩種授權類型。

以下是兩種授權類型：

* [資料處理單元(DPU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-bf589e13cf5c43a58f8f85a457de6f65)
* [檔案伺服器單元(FSU)](../../../home/c-inst-svr/c-install-ins-svr/c-abt-inst-svr-lic-units.md#section-8f3a5c8521a34913bbed10f5794b1a0a)

## 資料處理單元(DPU) {#section-bf589e13cf5c43a58f8f85a457de6f65}

此類型 [!DNL Insight Server] 可處理、儲存和提供Adobe資料集的資料。 它可以選擇儲存包含構建資料集的源資料的日誌檔案，也可以從檔案伺服器單元( [!DNL Insight Server] File Server Unit, FSU)接收該資料。 DPU是客戶與客戶 [!DNL Insight Server] 直接 [!DNL Insight] 互動 [!DNL Report] 的類型。

如果您要安裝 [!DNL Insight Server] DPU，請參 [閱Insight Server DPU的安裝程式](../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-proc-inst-svr-dpu.md#task-ce1ac85294604467ab750b24176d25bc)。

## 檔案伺服器單元(FSU) {#section-8f3a5c8521a34913bbed10f5794b1a0a}

此類型的伺服器可設定為從一或多個或事件資料複製例項( [!DNL Sensor] 具有特殊使用授權的功能)接收及儲存事件資料，並將資料串流至一或多個資料處理單元( [!DNL Repeater][!DNL Insight Server] DPU)，以建構Adobe資料集。 DPU使用協定與FSU通信，該協定優化了事件資料到DPU的傳輸，並且比維護普通檔案伺服器上的日誌檔案要快得多。 使用FSU還通過允許將日誌資料儲存在成本較低的儲存硬體上來降低硬體成本，並通過允許多個資料指向單個資料來降低 [!DNL Sensors] 管理複雜性 [!DNL Insight Server]。

如果要安裝FSU，請參 [!DNL Insight Server] 閱Insight Server [FSU的安裝程式](../../../home/c-inst-svr/c-install-ins-svr/t-inst-proc-fsu.md#task-e4a4a791b6694119ba45b36f3e573016)。
