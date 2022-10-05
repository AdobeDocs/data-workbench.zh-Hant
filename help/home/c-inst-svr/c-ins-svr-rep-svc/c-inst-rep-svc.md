---
description: Insight Server復寫服務可讓您將收集並儲存在一個Insight Server電腦上的事件資料傳輸至另一個Insight Server電腦。
title: 安裝複寫服務
uuid: a6467d5f-ca1c-4368-ba83-0b6bcabbe511
exl-id: a235fe75-a6d0-4c20-8ea2-8b1cbad12da7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 4%

---

# 安裝複寫服務{#installing-the-replication-service}

{{eol}}

Insight Server復寫服務可讓您將收集並儲存在一個Insight Server電腦上的事件資料傳輸至另一個Insight Server電腦。

通常，收集和儲存資料的電腦設定為以 [!DNL Repeater] 機器。 請參閱 [中繼器功能](../../../home/c-inst-svr/c-rptr-fntly/c-rptr-fntly.md). 此 [!DNL Replication Service]，此設定由 [!DNL Replicate.cfg] 檔案，啟用 [!DNL Insight Server] 從中檢索資料的電腦 [!DNL Repeater] 機器並儲存在本地。 此 [!DNL Insight Server] 電腦稱為目標電腦。 多個 [!DNL Insight Server] DPU可連線至單一 [!DNL Repeater] 請求事件資料的復本以納入多個資料集。

您可以使用 [!DNL Replication Service] 在具有多層防火牆的網路基礎設施中，實現由防火牆分隔的元件之間的單埠到單埠通信。

**若要安裝[!DNL Replication Service]**

此 [!DNL Replicate.cfg] 檔案應安裝為 [!DNL Insight Server] 安裝。 您可以在 [!DNL Components] 資料夾 [!DNL Insight Server] 安裝目錄。 如果您沒有此檔案，請聯絡Adobe。
