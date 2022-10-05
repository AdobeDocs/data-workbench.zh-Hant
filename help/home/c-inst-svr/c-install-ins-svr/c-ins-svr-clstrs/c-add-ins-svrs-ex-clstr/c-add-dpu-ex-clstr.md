---
description: 通常，當您要處理且讓Insight & Report的使用者存取的資料量超過叢集目前設定的容量時，您會想要將Insight Server DPU新增至現有叢集。
title: 將 Insight Server DPU 新增至現有叢集
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# 將 Insight Server DPU 新增至現有叢集{#adding-an-insight-server-dpu-to-an-existing-cluster}

{{eol}}

通常，當您要處理且讓Insight &amp; Report的使用者存取的資料量超過叢集目前設定的容量時，您會想要將Insight Server DPU新增至現有叢集。

## 更新主伺服器上的配置檔案 {#section-7c9a23754a994d73b722d53f999f0e82}

在 [!DNL Insight]，開啟 [!DNL Server Files Manager] 你的主人 [!DNL Insight Server] (通常是 [!DNL Insight Server] FSU)，並針對您要新增至叢集的每個DPU執行下列動作：

1. 編輯主版上的地址檔案 [!DNL Insight Server] 納入新DPU的名稱和位址，如 [將處理分析伺服器新增至位址檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). 將新DPU的名稱和地址新增至叢集目前所在的群組 [!DNL Insight Servers] 清單中。

1. 在主版上編輯訪問控制檔案 [!DNL Insight Server] 納入新DPU的IP位址，如 [更新群集的訪問控制檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## 安裝新的Insight Server DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

此任務僅適用於Windows 32位。

1. 將下列目錄從叢集中的其中一個目前DPU複製到新DPU:

   * [!DNL Insight Server] 安裝目錄/bin/
   * [!DNL Insight Server] 安裝目錄/證書/
   * [!DNL Insight Server] 安裝目錄/元件/

1. 下載並安裝新DPU的數位憑證，如 [下載和安裝數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. 在新DPU上設定Windows記憶體利用率參數。
1. 註冊 [!DNL Insight Server] 在新DPU電腦上作為Windows服務，如 [將Insight Server註冊為Windows服務](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. 檢查追蹤記錄，以確定DPU正在同步至主版 [!DNL Insight Server].
1. 對要添加到群集的每個附加DPU重複步驟1到6。

## 將新的Insight Server DPU新增至資料集設定檔的處理伺服器 {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

如果新DPU處理的資料集與叢集中的其他DPU相同，請將新DPU的通用名稱新增至 [!DNL profile.cfg] 主檔案 [!DNL Insight Server] 如 [在Profile.cfg中指定處理伺服器](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
