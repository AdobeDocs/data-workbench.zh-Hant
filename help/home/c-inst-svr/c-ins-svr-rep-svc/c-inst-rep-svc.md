---
description: Insight Server復寫服務可讓您將收集並儲存在一個Insight Server電腦上的事件資料傳輸至另一個Insight Server電腦。
title: 安裝複寫服務
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# 安裝複寫服務{#installing-the-replication-service}

Insight Server復寫服務可讓您將收集並儲存在一個Insight Server電腦上的事件資料傳輸至另一個Insight Server電腦。

通常，收集和儲存資料的電腦配置為作為[!DNL Repeater]電腦運行。 請參閱[中繼器功能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)。 [!DNL Replication Service]由[!DNL Replicate.cfg]檔案配置，使[!DNL Insight Server]電腦能夠從[!DNL Repeater]電腦中檢索資料並將其本地儲存。 [!DNL Insight Server]電腦稱為目標電腦。 多個[!DNL Insight Server] DPU可連線至單一[!DNL Repeater]，以要求事件資料的復本以納入多個資料集。

您可以在具有多層防火牆的網路基礎設施中使用[!DNL Replication Service]，在由防火牆分隔的元件之間實現單埠到單埠通信。

**若要安裝[!DNL Replication Service]**

[!DNL Replicate.cfg]檔案應作為[!DNL Insight Server]安裝的一部分進行安裝。 您可以在[!DNL Insight Server]安裝目錄的[!DNL Components]資料夾中找到該檔案。 如果您沒有此檔案，請聯絡Adobe。
