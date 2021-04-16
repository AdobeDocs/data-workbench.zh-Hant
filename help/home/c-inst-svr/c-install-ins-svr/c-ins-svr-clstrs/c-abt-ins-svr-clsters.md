---
description: 當您要處理並讓Insight和Report的使用者存取的資料量超過單一Insight Server的容量時，就需要Insight Server叢集。
title: 關於 Insight Server 叢集
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# 關於 Insight Server 叢集{#about-insight-server-clusters}

當您要處理並讓Insight和Report的使用者存取的資料量超過單一Insight Server的容量時，就需要Insight Server叢集。

通過設定[!DNL Insight Server]群集，您可以跨群集中的多台電腦分配單個分析資料集，以利用多台[!DNL Insight Servers]的處理能力。

實施[!DNL Insight Server]群集的第一步是在群集中分配[!DNL Insight Server]電腦。 您設定的第一個[!DNL Insight Server]機器是您的主要[!DNL Insight Server]（有時稱為您的主要[!DNL Insight Server]）。

>[!NOTE]
>
>如果您使用[!DNL Insight Server]檔案伺服器單元(FSU),Adobe建議您將FSU配置為主[!DNL Insight Server]。 有關配置FSU的資訊，請參見&#x200B;*資料集配置指南*。

主[!DNL Insight Server]管理群集中其它[!DNL Insight Servers]（稱為處理伺服器，有時稱為查詢伺服器）與[!DNL Insight]和[!DNL Report]實例之間的通信。 對於給定資料集，日誌檔案處理髮生在指定[!DNL Insight Servers]（主檔案或處理）的（一個或多個）上，如[!DNL Insight Server]配置檔案中指定。 在群集環境中工作時，[!DNL Insight]安裝配置為訪問主[!DNL Insight Server]，但可由群集中的任何[!DNL Insight Servers]處理查詢。

>[!NOTE]
>
>**PAServer.cfg**&#x200B;檔案。 如果您想要將Predictive Analytics叢集工作提交至Insight Server，則需要設定[!DNL PAServer.cfg]檔案，以處理伺服器端叢集提交。 自訂描述檔應繼承預測性分析描述檔([!DNL Server\Profiles\Predictive Analytics\Dataset])中的[!DNL PAServer.cfg]。 在此檔案中設定&#x200B;*主伺服器*，並將[!DNL PAServer.cfg]保存到實施站點。
>
>
```
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```

>[!IMPORTANT]
>
>本章中的說明不適用於建立由五個以上(5)[!DNL Insight Servers]組成的[!DNL Insight Server]群集。 請與Adobe聯繫，以取得超過5個[!DNL Insight Servers]的叢集的系統需求和描述檔設定建議。
