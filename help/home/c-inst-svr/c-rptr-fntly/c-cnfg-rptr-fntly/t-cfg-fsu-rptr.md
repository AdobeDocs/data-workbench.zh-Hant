---
description: 安裝和設定Insight Server FSU以搭配Repeater使用的指示。
solution: Analytics
title: 為中繼器設定 Insight Server FSU
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---


# 為中繼器設定 Insight Server FSU{#configuring-an-insight-server-fsu-for-repeater}

安裝和設定Insight Server FSU以搭配Repeater使用的指示。

依順序完成下列工作。 在每個步驟後都會記錄您必須進行的任何例外或變更， [!DNL Insight Server] 以便FSU可當成中繼伺服器使用。

1. 如安裝 [!DNL Insight Server] Insight Server中所述，安 [裝程式檔案](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd)。

   由於安裝這些檔案的機器會用來執行Repeater，因此請務必為安裝目錄提供描述性名稱，例如 [!DNL D:\Adobe\Repeater]。

1. 如下載 [!DNL Insight Server] 和安裝數位憑證 [中所述，安裝數位憑證](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)。

   登入Adobe授權伺服器後，請記得尋找符合指定中繼器電腦之伺服器公用名稱的憑證名稱。

1. 按照檢查埠設定中 [!DNL Communications.cfg] 所述檢查文 [件中的埠設定](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)。

   如果在同一台電腦上運行的另一個進程使用分配的埠（埠和SSL埠），則必須將埠分配更改為未使用的對。

1. 如有必要，請更改要在此電腦上 [!DNL Sensor] 收集和儲存的資料的日誌目錄。 如需指示，請參 [閱監視事件資料空間](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)。
1. 修改文 [!DNL Access Control.cfg] 件，允許管理訪問，如 [!DNL Insight Server] 更 [!DNL Insight] 新訪問控制 [檔案中所述](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)。
1. 修改檔 [!DNL server.address] 案以定義伺服器的網路位置，如定 [義伺服器的網路位置中所定義](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)。
1. 設定Windows記憶體使用參數。
1. 如注 [!DNL Insight Server] 冊Insight Server為Windows服務 [中所述，註冊為Windows服務](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)。
