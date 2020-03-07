---
description: Insight ServerReplication Service可讓您將收集並儲存在一台Insight Server機器上的事件資料傳輸至另一台Insight Server機器。
solution: Insight
title: 安裝複製服務
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 安裝複製服務{#installing-the-replication-service}

Insight ServerReplication Service可讓您將收集並儲存在一台Insight Server機器上的事件資料傳輸至另一台Insight Server機器。

通常，收集和儲存資料的電腦配置為作為電腦運 [!DNL Repeater] 行。 請參閱 [重複項功能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md)。 由 [!DNL Replication Service]檔案配置的 [!DNL Replicate.cfg] 設備使設備能夠從設備 [!DNL Insight Server] 中檢索資料並將其儲存到本 [!DNL Repeater] 地。 該 [!DNL Insight Server] 電腦稱為目標電腦。 多個 [!DNL Insight Server] DPU可以連線至單一DPU，以 [!DNL Repeater] 要求事件資料的復本，以便納入多個資料集。

您可以在具有 [!DNL Replication Service] 多層防火牆的網路基礎架構中使用，在防火牆分隔的元件之間實現單埠到單埠通信。

**若要安裝[!DNL Replication Service]**

檔 [!DNL Replicate.cfg] 案應安裝為安裝的一 [!DNL Insight Server] 部分。 您可以在安裝目錄的資 [!DNL Components] 料夾中找 [!DNL Insight Server] 到檔案。 如果您沒有此檔案，請聯絡Adobe。
