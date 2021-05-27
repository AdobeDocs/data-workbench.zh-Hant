---
description: 當您要處理且可供Insight及Report的使用者存取的資料量超過單一Insight Server的容量時，即需要Insight Server叢集。
title: 關於 Insight Server 叢集
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# 關於 Insight Server 叢集{#about-insight-server-clusters}

當您要處理且可供Insight及Report的使用者存取的資料量超過單一Insight Server的容量時，即需要Insight Server叢集。

通過設定[!DNL Insight Server]群集，您可以將單個分析資料集分佈到群集中的多台電腦，以利用多台[!DNL Insight Servers]的處理能力。

[!DNL Insight Server]群集實施的第一步是在群集中分配[!DNL Insight Server]電腦。 您設定的第一個[!DNL Insight Server]電腦是主[!DNL Insight Server]（有時稱為主[!DNL Insight Server]）。

>[!NOTE]
>
>如果使用[!DNL Insight Server]檔案伺服器單元(FSU),Adobe建議將FSU配置為主[!DNL Insight Server]。 如需設定FSU的相關資訊，請參閱&#x200B;*資料集設定指南*。

主[!DNL Insight Server]管理群集中其他[!DNL Insight Servers]（稱為處理伺服器，有時稱為查詢伺服器）與[!DNL Insight]和[!DNL Report]實例之間的通信。 對於指定的資料集，記錄檔處理會在[!DNL Insight Server]組態檔中指定的（一或多個）[!DNL Insight Servers]（主版或處理）上進行。 在群集環境中工作時，[!DNL Insight]安裝配置為訪問主[!DNL Insight Server]，但可由群集中的任何[!DNL Insight Servers]處理查詢。

>[!NOTE]
>
>**PAServer.cfg**&#x200B;檔案。 如果您想要將Predictive Analytics叢集作業提交至Insight Server，則需要設定[!DNL PAServer.cfg]檔案，以處理伺服器端叢集提交。 自訂設定檔應繼承預測分析設定檔的[!DNL PAServer.cfg]([!DNL Server\Profiles\Predictive Analytics\Dataset])。 在此檔案中設定&#x200B;*主伺服器*&#x200B;並將[!DNL PAServer.cfg]儲存到實作網站。
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
>本章中的說明不適用於建立[!DNL Insight Server]群集，該群集由五(5)[!DNL Insight Servers]組成。 請與Adobe聯繫，以獲取大於5個[!DNL Insight Servers]群集的系統要求和配置檔案配置建議。
