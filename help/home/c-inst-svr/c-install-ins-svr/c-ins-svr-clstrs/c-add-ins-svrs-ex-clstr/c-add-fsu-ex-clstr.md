---
description: 如果您想要將來源資料儲存在其他檔案伺服器上，或想設定主Insight Server的備份，則可能要將Insight Server FSU新增至現有叢集。
title: 將 Insight Server FSU 新增至現有叢集
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 將 Insight Server FSU 新增至現有叢集{#adding-an-insight-server-fsu-to-an-existing-cluster}

如果您想要將來源資料儲存在其他檔案伺服器上，或想設定主Insight Server的備份，則可能要將Insight Server FSU新增至現有叢集。

要將[!DNL Insight Server] FSU添加到現有群集，必須執行以下過程：

1. [更新主伺服器上的配置檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [安裝新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [設定新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## 更新主伺服器{#section-b5f21f2edb35493da4475de2cdeefca1}上的配置檔案

在[!DNL Insight]中，開啟主版[!DNL Insight Server]的[!DNL Server Files Manager]（通常為[!DNL Insight Server] FSU），然後對要添加到群集的每個FSU執行以下操作：

1. 編輯主版[!DNL Insight Server]上的地址檔案，以包含新FSU的名稱和地址，如[新增處理分析伺服器至地址檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)中所述。 將新FSU的名稱和地址添加到列出群集當前[!DNL Insight Servers]的組中。

1. 按[更新群集](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)的訪問控制檔案中所述，編輯主[!DNL Insight Server]上的訪問控制檔案以包括新FSU的IP地址。

## 安裝新的Insight Server FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 在您目前的FSU上，建立[!DNL Insight Server]安裝目錄的zip檔案，並將檔案複製到新的FSU。
1. 將檔案解壓縮至您要放置[!DNL Insight Server]軟體的位置。
1. 下載並安裝新FSU的數位憑證，如[下載和安裝數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)所述。
1. 在新FSU上設定Windows記憶體利用率參數。
1. 更改[!DNL .address]檔案的名稱以反映FSU的名稱，如[定義伺服器的網路位置](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)中所述。

1. 如果新FSU上的驅動器結構與主FSU上的驅動器結構不同，則需要編輯[!DNL Disk Files.cfg]檔案。

   1. 在新FSU上開啟[!DNL Disk Files.cfg]檔案。
   1. 如[監控資料集資料空間](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)中所述，更新設定以匹配主FSU的驅動器。
   1. 將檔案儲存在本機並儲存至伺服器。

1. 如[將Insight Server註冊為Windows服務](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)所述，在新FSU電腦上將[!DNL Insight Server]註冊為Windows服務。

1. 對要添加到群集的每個附加FSU重複步驟1到6。

## 配置新的Insight Server FSU {#section-c39334c5bd754d5b98d41ad094333108}

以下過程提供了特定配置任務的說明。 請依照適合您實作新FSU的指示操作。

**配置源資料儲存的FSU**

如果新的FSU儲存運行在群集上的資料集的其他源資料，則必須按照&#x200B;*資料集配置指南*&#x200B;的「日誌處理配置檔案」一章中的「配置[!DNL Insight Server]檔案伺服器單元」中所述完成檔案伺服器配置過程。

**為新FSU建立主FSU的備 [!DNL Insight Server] 份**

如果要將新FSU設為主[!DNL Insight Server]的備份（用作群集的FSU），則必須修改新（備份）FSU上的同步檔案，使其與主FSU同步。

1. 在備份[!DNL Insight Server] FSU上，使用[!DNL Server Files Manager]將[!DNL Components for Processing Servers]資料夾中的[!DNL Synchronize.cfg]檔案複製到[!DNL Components]資料夾。

1. 開啟[!DNL Insight]中的[!DNL Synchronize.cfg]檔案（在[!DNL Components]資料夾中）。

1. 查找指定元件目錄位置的SynchronizeDir。 「目錄」下可能列出了多個同步目錄，因此您可能需要查看其中許多目錄的內容（通過按一下伺服器號）以查找所需的伺服器。
1. 編輯SynchronizeDir條目並添加第二個SynchronizeDir條目，如下例所示。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 以新名稱（如[!DNL FSU_Synchronize.cfg]）保存修改的檔案，這樣您就不會將其與群集中DPU上的[!DNL Synchronize.cfg]檔案混淆。

1. 使用[!DNL Server Files Manager]將更名檔案的本地副本保存到伺服器。 備份FSU從主[!DNL Insight Server] FSU下載所標識目錄中的檔案，並在更改時從主[!DNL Insight Server] FSU動態檢索這些檔案的更新副本。
