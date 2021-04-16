---
description: 若要使用叢集，您必須在叢集中指定一個Insight Server，以擔任主Insight Server。
title: 安裝主 Insight Server
uuid: a73214f3-b175-4e9e-8802-7a8451d86d3a
exl-id: 710f1ffe-f620-4920-b4f9-a644cc68d4cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 5%

---

# 安裝主 Insight Server{#installing-the-master-insight-server}

若要使用叢集，您必須在叢集中指定一個Insight Server，以擔任主Insight Server。

客戶機元件（如[!DNL Insight]或[!DNL Report]）在會話開始時連接到主[!DNL Insight Server]。 在會話期間的後續點，客戶機可能連接到群集中的其他[!DNL Insight Servers]以執行查詢。 客戶機和群集中其它[!DNL Insight Servers]之間的這些後續連接由主[!DNL Insight Server]協調，並且對客戶機透明。

除了協調客戶機與群集中其他[!DNL Insight Servers]之間的連接外，主[!DNL Insight Server]還充當整個群集的中央管理點。 在管理群集時，請更新主[!DNL Insight Server]。 群集中其他[!DNL Insight Servers]將檢索您在主[!DNL Insight Server]上所做的管理更改。

**安裝主版[!DNL Insight Server]**

1. 確定哪個電腦將充當主[!DNL Insight Server]。
1. 如[ Insight Server](../../../../../../home/c-inst-svr/c-msr-server/c-msr-server.md)所述，在此機器上安裝及設定[!DNL Insight Server]（通常為[!DNL Insight Server] FSU）。
1. 安裝[!DNL Insight]並按照&#x200B;*[!DNL Insight]使用手冊*&#x200B;中的說明配置到主[!DNL Insight Server]的連接。
