---
description: 安裝及設定Insight Server FSU以與中繼器搭配使用的指示。
title: 為中繼器設定 Insight Server FSU
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# 為中繼器設定 Insight Server FSU{#configuring-an-insight-server-fsu-for-repeater}

{{eol}}

安裝及設定Insight Server FSU以與中繼器搭配使用的指示。

請依序完成下列工作。 您必須進行的任何例外或變更， [!DNL Insight Server] FSU可作為中繼器伺服器，在每個步驟後都會記錄。

1. 安裝 [!DNL Insight Server] 程式檔案，如 [安裝Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   因為安裝這些檔案的電腦會用來執行中繼器，所以為安裝目錄指定描述性名稱(例如 [!DNL D:\Adobe\Repeater].

1. 安裝 [!DNL Insight Server] 數字證書，如 [下載和安裝數位憑證](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   登入Adobe授權伺服器後，請記得尋找與指定中繼器電腦的伺服器通用名稱相符的憑證名稱。

1. 檢查 [!DNL Communications.cfg] 檔案，如 [檢查埠設定](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   如果分配的埠（埠和SSL埠）被同一台電腦上運行的另一個進程使用，則必須將埠分配更改為未使用的對。

1. 如有必要，請變更 [!DNL Sensor] 要在此電腦上收集和儲存的資料。 如需指示，請參閱 [監控事件資料空間](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. 修改 [!DNL Access Control.cfg] 允許管理訪問的檔案 [!DNL Insight Server] 從 [!DNL Insight] 如 [更新存取控制檔案](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. 修改 [!DNL server.address] 檔案，按照 [定義伺服器的網路位置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. 設定Windows記憶體利用率參數。
1. 註冊 [!DNL Insight Server] as a Windows服務，如 [將Insight Server註冊為Windows服務](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
