---
description: Insight ServerReplication Service可讓您將收集並儲存在一台Insight Server機器上的事件資料傳輸至另一台Insight Server機器。
title: 安裝複寫服務
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# 安裝複寫服務{#installing-the-replication-service}

Insight ServerReplication Service可讓您將收集並儲存在一台Insight Server機器上的事件資料傳輸至另一台Insight Server機器。

通常，收集和儲存資料的電腦配置為作為[!DNL Repeater]電腦運行。 請參閱[中繼器功能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)。 [!DNL Replication Service]由[!DNL Replicate.cfg]檔案配置，使[!DNL Insight Server]電腦能夠從[!DNL Repeater]電腦檢索資料並將其儲存在本地。 [!DNL Insight Server]電腦稱為目標電腦。 多個[!DNL Insight Server] DPU可連接至單個[!DNL Repeater]以請求事件資料的拷貝以包含在多個資料集中。

您可以在具有多層防火牆的網路基礎架構中使用[!DNL Replication Service]，在由防火牆分隔的元件之間實現單埠到單埠的通信。

**若要安裝[!DNL Replication Service]**

應將[!DNL Replicate.cfg]檔案作為[!DNL Insight Server]安裝的一部分進行安裝。 您可以在[!DNL Insight Server]安裝目錄的[!DNL Components]資料夾中找到該檔案。 如果您沒有此檔案，請聯絡Adobe。
