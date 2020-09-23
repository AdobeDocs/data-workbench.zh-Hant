---
description: 若要使用叢集，您必須在叢集中指定一個Insight Server，以擔任主Insight Server。
solution: Analytics
title: 安裝主 Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---


# 安裝主 Insight Server{#installing-the-master-insight-server}

若要使用叢集，您必須在叢集中指定一個Insight Server，以擔任主Insight Server。

客戶端元件( [!DNL Insight] 如 [!DNL Report] 或)在會話 [!DNL Insight Server] 開始時連接到主設備。 在會話期間的後續點，客戶端可能連接到群集中 [!DNL Insight Servers] 的其他節點以執行查詢。 客戶機和群集中的其它設備之 [!DNL Insight Servers] 間的這些後續連接由主機協調， [!DNL Insight Server] 並且對客戶機透明。

除了在群集中協調客戶端與其 [!DNL Insight Servers] 他客戶端之間的連接外，主機還 [!DNL Insight Server] 充當整個群集的中心管理點。 在管理群集時，您會更新主群集 [!DNL Insight Server]。 群集中的其他成員將檢索您在主 [!DNL Insight Server] 版上所做的管 [!DNL Insight Servers] 理更改。

**安裝主版[!DNL Insight Server]**

1. 確定哪台機器將充當主機 [!DNL Insight Server]。
1. 如 [!DNL Insight Server] Insight Server [!DNL Insight Server] 所述，在 [此機器上安裝及設定（通常為FSU）](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)。
1. 按照 [!DNL Insight] 使用手冊中的說明，安 [!DNL Insight Server] 裝並配置到主 *[!DNL Insight]版的連接*。
