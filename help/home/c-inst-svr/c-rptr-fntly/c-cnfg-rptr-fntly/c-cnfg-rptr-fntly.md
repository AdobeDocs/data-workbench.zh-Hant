---
description: 中繼器功能可讓Insight Server FSU接收來自一或多個來源的感測器擷取事件資料，並將資料複製至執行Insight Server復寫服務的一或多個Insight Server FSU。
title: 設定中繼器功能
uuid: 45dca069-a91f-4fd4-bd47-c8c2e6aab834
exl-id: 61b70772-07fb-4963-b09f-6b2cf97b01a1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 9%

---

# 設定中繼器功能{#configuring-repeater-functionality}

中繼器功能可讓Insight Server FSU接收來自一或多個來源的感測器擷取事件資料，並將資料複製至執行Insight Server復寫服務的一或多個Insight Server FSU。

請參閱[Insight Server復寫服務](../../../../home/c-inst-svr/c-ins-svr-rep-svc/c-ins-svr-rep-svc.md#concept-926e654e80d943a0b6ac44a82a510d92)。 此功能允許將資料複製到冗餘設施以用於災難恢復。 目標伺服器充當網路客戶端，連接到源FSU以請求事件資料的副本以包含在多個資料集中。

您可以在具有多層防火牆的網路基礎設施中使用中繼器功能，在由防火牆分隔的元件之間實現單埠到單埠的通信。

有關安裝、配置和操作[!DNL Repeater]的系統需求的資訊，請參閱&#x200B;*最低系統需求*&#x200B;文檔。

要安裝[!DNL Repeater]，必須執行以下兩個過程所列的步驟：

* [為中繼器設定 Insight Server FSU](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-fsu-rptr.md#task-1ad7fa5777b845f4bd398f97226e56b2)
* [為目標機器設定存取控制](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-cfg-acc-ctrll-tgt-mach.md#task-0e49953728444839bc0a26234501a4c5)

如果網路防火牆允許從[!DNL Insight]存取您的[!DNL Repeater]，您可以依照[在Insight和中繼器之間建立連線](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118)中所述建立連線。
