---
description: 安裝和設定Insight Server FSU以搭配Repeater使用的指示。
title: 為中繼器設定 Insight Server FSU
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# 為中繼器設定 Insight Server FSU{#configuring-an-insight-server-fsu-for-repeater}

安裝和設定Insight Server FSU以搭配Repeater使用的指示。

依順序完成下列工作。 每個步驟後都會記錄您必須進行的任何例外或變更，以便[!DNL Insight Server] FSU可當成中繼器伺服器。

1. 按照[安裝Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)中所述安裝[!DNL Insight Server]程式檔案。

   由於安裝這些檔案的電腦用於運行Repeater，因此為安裝目錄提供描述性名稱（如[!DNL D:\Adobe\Repeater]）很有幫助。

1. 按照[下載和安裝數字證書](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)中所述安裝[!DNL Insight Server]數字證書。

   登入Adobe授權伺服器後，請記得尋找符合指定中繼器電腦之伺服器公用名稱的憑證名稱。

1. 按照[檢查埠設定](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)中所述檢查[!DNL Communications.cfg]檔案中的埠設定。

   如果在同一台電腦上運行的另一個進程使用分配的埠（埠和SSL埠），則必須將埠分配更改為未使用的對。

1. 如有必要，請更改要在此電腦上收集和儲存的[!DNL Sensor]資料的日誌目錄。 有關說明，請參閱[監視事件資料空間](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)。
1. 修改[!DNL Access Control.cfg]檔案，允許從[!DNL Insight]管理訪問[!DNL Insight Server]，如[更新訪問控制檔案](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)中所述。
1. 修改[!DNL server.address]檔案以定義伺服器的網路位置，如[定義伺服器的網路位置](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)中所定義。
1. 設定Windows記憶體使用參數。
1. 如[將Insight Server註冊為Windows服務](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)中所述，將[!DNL Insight Server]註冊為Windows服務。
