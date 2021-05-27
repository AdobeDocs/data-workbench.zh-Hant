---
description: 安裝及設定Insight Server FSU以與中繼器搭配使用的指示。
title: 為中繼器設定 Insight Server FSU
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# 為中繼器設定 Insight Server FSU{#configuring-an-insight-server-fsu-for-repeater}

安裝及設定Insight Server FSU以與中繼器搭配使用的指示。

請依序完成下列工作。 每個步驟後都會記錄您必須執行的任何例外或變更，以便[!DNL Insight Server] FSU可作為中繼器伺服器使用。

1. 如[安裝Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)中所述，安裝[!DNL Insight Server]程式檔案。

   因為安裝這些檔案的電腦用於運行中繼器，所以為安裝目錄提供描述性名稱（如[!DNL D:\Adobe\Repeater]）很有幫助。

1. 依照[下載和安裝數位憑證](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)中所述，安裝[!DNL Insight Server]數位憑證。

   登入Adobe授權伺服器後，請記得尋找與指定中繼器電腦的伺服器通用名稱相符的憑證名稱。

1. 如[檢查埠設定](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)中所述，檢查[!DNL Communications.cfg]檔案中的埠設定。

   如果分配的埠（埠和SSL埠）被同一台電腦上運行的另一個進程使用，則必須將埠分配更改為未使用的對。

1. 如有必要，請更改要在此電腦上收集和儲存的[!DNL Sensor]資料的日誌目錄。 有關說明，請參閱[監視事件資料空間](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)。
1. 修改[!DNL Access Control.cfg]檔案，以允許管理訪問[!DNL Insight]，如[更新訪問控制檔案](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)中所述。[!DNL Insight Server]
1. 修改[!DNL server.address]檔案以按照[定義伺服器的網路位置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)中的定義來定義伺服器的網路位置。
1. 設定Windows記憶體利用率參數。
1. 如[將Insight Server註冊為Windows服務](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)中所述，將[!DNL Insight Server]註冊為Windows服務。
