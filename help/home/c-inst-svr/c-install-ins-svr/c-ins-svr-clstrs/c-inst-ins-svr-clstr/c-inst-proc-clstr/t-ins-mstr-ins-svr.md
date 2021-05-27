---
description: 若要使用叢集，您必須在叢集中指定一個Insight Server作為主Insight Server。
title: 安裝主 Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# 安裝主 Insight Server{#installing-the-master-insight-server}

若要使用叢集，您必須在叢集中指定一個Insight Server作為主Insight Server。

客戶端元件（如[!DNL Insight]或[!DNL Report]）在會話開始時連接到主[!DNL Insight Server]。 在會話期間的後續點，客戶端可能連接到群集中的其他[!DNL Insight Servers]以執行查詢。 客戶機和群集中的其他[!DNL Insight Servers]之間的後續連接由主[!DNL Insight Server]牽線，並且對客戶機透明。

除了代理客戶機與群集中的其他[!DNL Insight Servers]之間的連接外，主[!DNL Insight Server]還充當整個群集的中央管理點。 管理群集時，需更新主[!DNL Insight Server]。 您在主[!DNL Insight Server]上所做的管理更改由群集中的其他[!DNL Insight Servers]檢索。

**安裝主版[!DNL Insight Server]**

1. 確定將哪個電腦作為主[!DNL Insight Server]。
1. 在此電腦上安裝並配置[!DNL Insight Server]（通常為[!DNL Insight Server] FSU），如[Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)中所述。
1. 安裝[!DNL Insight]並配置與主[!DNL Insight Server]的連接，如&#x200B;*[!DNL Insight]使用手冊*&#x200B;中所述。
