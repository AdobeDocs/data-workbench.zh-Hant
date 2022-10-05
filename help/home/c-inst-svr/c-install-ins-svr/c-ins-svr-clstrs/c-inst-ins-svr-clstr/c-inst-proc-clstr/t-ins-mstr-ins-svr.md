---
description: 若要使用叢集，您必須在叢集中指定一個Insight Server作為主Insight Server。
title: 安裝主 Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# 安裝主 Insight Server{#installing-the-master-insight-server}

{{eol}}

若要使用叢集，您必須在叢集中指定一個Insight Server作為主Insight Server。

客戶端元件，如 [!DNL Insight] 或 [!DNL Report] 連接到主 [!DNL Insight Server] 會議開始時。 在工作階段期間的後續點，用戶端可能會連線至其他 [!DNL Insight Servers] 在叢集中以執行查詢。 客戶端和其他 [!DNL Insight Servers] 由主機牽線 [!DNL Insight Server] 且對客戶是透明的。

除了代理客戶與其他 [!DNL Insight Servers] 在群集中，主 [!DNL Insight Server] 充當整個群集的中心管理點。 管理群集時，請更新主伺服器 [!DNL Insight Server]. 您對主版所做的管理更改 [!DNL Insight Server] 由其他 [!DNL Insight Servers] 在叢集中。

**安裝主版[!DNL Insight Server]**

1. 確定將充當主機的電腦 [!DNL Insight Server].
1. 安裝和配置 [!DNL Insight Server] (通常， [!DNL Insight Server] FSU)，如 [Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md).
1. 安裝 [!DNL Insight] 並配置與主伺服器的連接 [!DNL Insight Server] 如 *[!DNL Insight]使用手冊*.
