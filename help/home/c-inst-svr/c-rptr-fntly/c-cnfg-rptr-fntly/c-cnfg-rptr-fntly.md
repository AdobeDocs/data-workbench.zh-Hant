---
description: 重複項功能可讓Insight Server FSU從一或多個來源接收感測器獲取的事件資料，並將資料複製到運行Insight ServerReplication Service的一個或多個Insight Server FSU。
solution: Insight
title: 設定重複項功能
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定重複項功能{#configuring-repeater-functionality}

重複項功能可讓Insight Server FSU從一或多個來源接收感測器獲取的事件資料，並將資料複製到運行Insight ServerReplication Service的一個或多個Insight Server FSU。

請參 [閱Insight Server Replication Service](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92)。 此功能允許將資料複製到冗餘設施，以用於災難恢復。 目標伺服器充當網路客戶機，連接到源FSU以請求事件資料的拷貝以便包含在多個資料集中。

您可以在具有多層防火牆的網路基礎架構中使用中繼器功能，在由防火牆分隔的元件之間實現單埠到單埠通訊。

有關安裝、配置和作業系統需求的資訊，請參 [!DNL Repeater]閱最低系 *統需求文檔* 。

要安裝， [!DNL Repeater]您必須執行下列兩個步驟的步驟：

* [為中繼器設定Insight Server FSU](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [為目標電腦配置訪問控制](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

如果網路防火牆允許您從存取 [!DNL Repeater] 您的 [!DNL Insight]網路，您可以建立連線，如 [Creating a Connection Between Insight and Repeater中所述](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)。
