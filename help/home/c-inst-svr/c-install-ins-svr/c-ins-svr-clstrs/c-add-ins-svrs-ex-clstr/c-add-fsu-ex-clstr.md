---
description: 如果您想要將來源資料儲存在其他檔案伺服器上，或想為主Insight伺服器設定備份，則可能想要將Insight Server FSU新增至現有叢集。
solution: Insight
title: 將Insight Server FSU添加到現有群集
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 將Insight Server FSU添加到現有群集{#adding-an-insight-server-fsu-to-an-existing-cluster}

如果您想要將來源資料儲存在其他檔案伺服器上，或想為主Insight伺服器設定備份，則可能想要將Insight Server FSU新增至現有叢集。

要將 [!DNL Insight Server] FSU添加到現有群集，必須執行以下過程：

1. [在主伺服器上更新配置檔案](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [安裝新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [設定新的Insight Server FSU](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## 在主伺服器上更新配置檔案 {#section-b5f21f2edb35493da4475de2cdeefca1}

在 [!DNL Insight]中，為主 [!DNL Server Files Manager] 設備(通常為 [!DNL Insight Server][!DNL Insight Server] FSU)開啟，然後對要添加到群集的每個FSU執行以下操作：

1. 編輯主版上的地址檔 [!DNL Insight Server] 案，以包含新FSU的名稱和位址，如將處理分析伺服器新 [增至位址檔中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)。 將新FSU的名稱和位址新增至叢集目前所列的群 [!DNL Insight Servers] 組。

1. 編輯主版上的訪問控制文 [!DNL Insight Server] 件，以包括新FSU的IP地址，如更新群 [集的訪問控制檔案中所述](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b)。

## 安裝新的Insight Server FSU {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. 在您目前的FSU上，建立安裝目錄的zip [!DNL Insight Server] 檔案，並將檔案複製到新的FSU。
1. 將檔案解壓縮至您要放置軟體的位 [!DNL Insight Server] 置。
1. 依照下載和安裝數位憑證中所述，下載並安裝新 [FSU的數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。
1. 在新FSU上設定Windows記憶體使用參數。
1. 更改檔案名 [!DNL .address] 以反映FSU的名稱，如定義服 [務器網路位置中所述](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。

1. 如果新FSU上的驅動器結構與主FSU上的驅動器結構不同，則需要編輯文 [!DNL Disk Files.cfg] 件。

   1. 在新的 [!DNL Disk Files.cfg] FSU上開啟檔案。
   1. 如監視資料集資料空間中所述，更新設定以匹配主FSU [的驅動器](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03)。
   1. 將檔案儲存在本機並儲存至伺服器。

1. 在新 [!DNL Insight Server] 的FSU機器上註冊為Windows服務，如注 [冊Insight Server為Windows服務中所述](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。

1. 對要添加到群集的每個附加FSU重複步驟1到6。

## 設定新的Insight Server FSU {#section-c39334c5bd754d5b98d41ad094333108}

以下過程提供了特定配置任務的說明。 請依照適合您實作新FSU的指示進行。

**配置源資料儲存的FSU**

如果新的FSU儲存了在群集上運行的資料集的其他源資料，則必須按照《資料集配置指南》的「日誌處理配置檔案」一章中的「配置檔案伺服器單元」中的說明完成檔案伺服器配置 [!DNL Insight Server] 過程 **。

**使新FSU成為主[!DNL Insight Server]FSU的備份**

如果要將新FSU作為主FSU的備份 [!DNL Insight Server] （作為群集的FSU），則必須修改新（備份）FSU上的同步檔案，以便與主FSU同步。

1. 在備份 [!DNL Insight Server] FSU中，使用 [!DNL Server Files Manager] 將資料夾 [!DNL Synchronize.cfg] 中的文 [!DNL Components for Processing Servers] 件複製到文 [!DNL Components] 件夾。

1. 在中開啟 [!DNL Synchronize.cfg] 檔案(在檔案 [!DNL Components] 夾中) [!DNL Insight]。

1. 查找指定「元件」目錄位置的SynchronizeDir。 「目錄」下可能列出多個同步目錄，因此您可能需要查看其中許多目錄的內容（通過按一下伺服器號）以查找所需的伺服器。
1. 編輯SynchronizeDir條目並添加第二個SynchronizeDir條目，如下例所示。

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. 使用新名稱（例如）保存修改的 [!DNL FSU_Synchronize.cfg] 檔案，以便不將其與群集中 [!DNL Synchronize.cfg] DPU上的檔案混淆。

1. 使用 [!DNL Server Files Manager] 將更名的檔案的本地副本保存到伺服器。 備份FSU從主 [!DNL Insight Server] FSU下載所標識目錄中的檔案，並在更改時從主 [!DNL Insight Server] FSU動態檢索這些檔案的更新副本。

