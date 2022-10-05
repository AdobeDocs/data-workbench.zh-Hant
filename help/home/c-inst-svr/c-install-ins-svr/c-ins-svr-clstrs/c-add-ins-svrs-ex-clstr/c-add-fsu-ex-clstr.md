---
description: 如果您想要將來源資料儲存在其他檔案伺服器上，或想設定主Insight Server的備份，則可能要將Insight Server FSU新增至現有叢集。
title: 將 Insight Server FSU 新增至現有叢集
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# 將 Insight Server FSU 新增至現有叢集{#adding-an-insight-server-fsu-to-an-existing-cluster}

{{eol}}

如果您想要將來源資料儲存在其他檔案伺服器上，或想設定主Insight Server的備份，則可能要將Insight Server FSU新增至現有叢集。

新增 [!DNL Insight Server] FSU到現有群集時，必須執行以下過程：

1. [更新主伺服器上的配置檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [安裝新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [設定新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## 更新主伺服器上的配置檔案 {#section-b5f21f2edb35493da4475de2cdeefca1}

在 [!DNL Insight]，開啟 [!DNL Server Files Manager] 你的主人 [!DNL Insight Server] (通常是 [!DNL Insight Server] FSU)，並針對要新增至叢集的每個FSU執行下列動作：

1. 編輯主版上的地址檔案 [!DNL Insight Server] 包括新FSU的名稱和地址，如 [將處理分析伺服器新增至位址檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). 將新FSU的名稱和地址添加到群集當前所在的組 [!DNL Insight Servers] 清單中。

1. 在主版上編輯訪問控制檔案 [!DNL Insight Server] 包括新FSU的IP地址，如 [更新群集的訪問控制檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## 安裝新的Insight Server FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 在您目前的FSU上，建立 [!DNL Insight Server] 安裝目錄，並將檔案複製到新FSU。
1. 將檔案解壓縮至您要放置的位置 [!DNL Insight Server] 軟體。
1. 下載並安裝新FSU的數位憑證，如 [下載和安裝數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. 在新FSU上設定Windows記憶體利用率參數。
1. 變更 [!DNL .address] 檔案，以反映FSU的名稱，如 [定義伺服器的網路位置](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. 如果新FSU上的驅動器結構與主FSU上的驅動器結構不同，則需要編輯 [!DNL Disk Files.cfg] 檔案。

   1. 開啟 [!DNL Disk Files.cfg] 檔案。
   1. 更新設定以匹配主FSU的驅動器，如 [監控資料集資料空間](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. 將檔案儲存在本機並儲存至伺服器。

1. 註冊 [!DNL Insight Server] 作為新FSU電腦上的Windows服務，如 [將Insight Server註冊為Windows服務](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. 對要添加到群集的每個附加FSU重複步驟1到6。

## 設定新的Insight Server FSU {#section-c39334c5bd754d5b98d41ad094333108}

以下過程提供了特定配置任務的說明。 請依照適合您實作新FSU的指示操作。

**配置源資料儲存的FSU**

如果新的FSU儲存在叢集上執行之資料集的其他來源資料，您必須依照設定 [!DNL Insight Server] 檔案伺服器單元，位於 *資料集組態指南*.

**為新FSU建立主備份 [!DNL Insight Server] FSU**

如果希望將新FSU設為主備份 [!DNL Insight Server] （它用作群集的FSU），必須修改新（備份）FSU上的同步檔案，使其與主FSU同步。

1. 備份 [!DNL Insight Server] FSU，使用 [!DNL Server Files Manager] 複製 [!DNL Synchronize.cfg] 檔案 [!DNL Components for Processing Servers] 檔案夾 [!DNL Components] 檔案夾。

1. 開啟 [!DNL Synchronize.cfg] 檔案(在 [!DNL Components] 資料夾) [!DNL Insight].

1. 查找指定元件目錄位置的SynchronizeDir。 「目錄」下可能列出了多個同步目錄，因此您可能需要查看其中許多目錄的內容（通過按一下伺服器號）以查找所需的伺服器。
1. 編輯SynchronizeDir條目並添加第二個SynchronizeDir條目，如下例所示。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 以新名稱(如 [!DNL FSU_Synchronize.cfg] 這樣你才不會把它和 [!DNL Synchronize.cfg] 檔案。

1. 使用 [!DNL Server Files Manager] 將更名檔案的本地副本保存到伺服器。 備份FSU從主目錄下載所標識目錄中的檔案 [!DNL Insight Server] FSU並從主版中動態擷取這些檔案的更新副本 [!DNL Insight Server] FSU變化。
