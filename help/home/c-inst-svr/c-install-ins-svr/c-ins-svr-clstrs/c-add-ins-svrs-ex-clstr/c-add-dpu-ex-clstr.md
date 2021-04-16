---
description: 通常，當您要處理並讓Insight和Report的使用者存取的資料量超過叢集目前組態的容量時，您會想要將Insight Server DPU新增至現有叢集。
title: 將 Insight Server DPU 新增至現有叢集
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# 將 Insight Server DPU 新增至現有叢集{#adding-an-insight-server-dpu-to-an-existing-cluster}

通常，當您要處理並讓Insight和Report的使用者存取的資料量超過叢集目前組態的容量時，您會想要將Insight Server DPU新增至現有叢集。

## 更新主伺服器{#section-7c9a23754a994d73b722d53f999f0e82}上的配置檔案

在[!DNL Insight]中，為主[!DNL Insight Server]（通常為[!DNL Insight Server] FSU）開啟[!DNL Server Files Manager]，並對要添加到群集的每個DPU執行以下操作：

1. 編輯主版[!DNL Insight Server]上的地址檔案，以包含新DPU的名稱和地址，如[將處理分析伺服器添加到地址檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)中所述。 將新DPU的名稱和位址新增至叢集目前[!DNL Insight Servers]所列的群組。

1. 編輯主[!DNL Insight Server]上的訪問控制檔案，以包括新DPU的IP地址，如[更新群集的訪問控制檔案中所述。](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)

## 安裝新Insight Server DPU {#section-8ce9a5957db24f94b3a3250caaccc7ba}

此任務僅適用於Windows 32位。

1. 將下列目錄從叢集中的其中一個目前DPU複製到新DPU:

   * [!DNL Insight Server] 安裝目錄/bin/
   * [!DNL Insight Server] 安裝目錄／證書/
   * [!DNL Insight Server] 安裝目錄／元件/

1. 下載並安裝新DPU的數位憑證，如[下載和安裝數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)所述。
1. 在新DPU上設定Windows記憶體使用參數。
1. 在新的DPU機器上將[!DNL Insight Server]註冊為Windows服務](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)，如[註冊Insight Server為Windows服務中所述。

1. 檢查跟蹤日誌以確保DPU與主[!DNL Insight Server]同步。
1. 對要添加到群集的每個附加DPU重複步驟1到6。

## 將新的Insight Server DPU新增至資料集描述檔的處理伺服器{#section-cdc6c3913b9f4010b5e17cc7ec85e849}

如果新DPU處理與叢集中其他DPU相同的資料集，請將新DPU的公用名稱新增至主[!DNL Insight Server]上的[!DNL profile.cfg]檔案，如[指定Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9)中的處理伺服器。
