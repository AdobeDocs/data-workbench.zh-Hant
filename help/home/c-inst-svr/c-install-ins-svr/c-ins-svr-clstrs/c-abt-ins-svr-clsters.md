---
description: 當您要處理且可供Insight及Report的使用者存取的資料量超過單一Insight Server的容量時，即需要Insight Server叢集。
title: 關於 Insight Server 叢集
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
exl-id: b26e0f63-76db-461d-91e7-0968624aa0f7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# 關於 Insight Server 叢集{#about-insight-server-clusters}

{{eol}}

當您要處理且可供Insight及Report的使用者存取的資料量超過單一Insight Server的容量時，即需要Insight Server叢集。

設定 [!DNL Insight Server] 叢集中，您可以在叢集中的多部電腦間散布單一分析資料集，以利用多部電腦的處理能力 [!DNL Insight Servers].

實施 [!DNL Insight Server] 群集將分配 [!DNL Insight Server] 群集中的電腦。 第一個 [!DNL Insight Server] 你設定的機器是主機 [!DNL Insight Server] (有時稱為主要 [!DNL Insight Server])。

>[!NOTE]
>
>如果您使用 [!DNL Insight Server] 檔案伺服器單元(FSU),Adobe建議您將FSU配置為主伺服器 [!DNL Insight Server]. 如需設定FSU的詳細資訊，請參閱 *資料集組態指南*.

主人 [!DNL Insight Server] 管理其他 [!DNL Insight Servers] （稱為處理伺服器，有時稱為查詢伺服器）和 [!DNL Insight] 和 [!DNL Report]. 若是指定的資料集，記錄檔會在指定的 [!DNL Insight Servers] （主版或處理），如 [!DNL Insight Server] 組態檔。 在群集環境中工作時， [!DNL Insight] 安裝配置為訪問主伺服器 [!DNL Insight Server]，但查詢可由任何 [!DNL Insight Servers] 在叢集內。

>[!NOTE]
>
>此 **PAServer.cfg** 檔案。 如果您想要將Predictive Analytics叢集作業提交至Insight Server，則需要設定 [!DNL PAServer.cfg] 處理伺服器端叢集提交的檔案。 自訂設定檔應繼承 [!DNL PAServer.cfg] 來自預測分析設定檔([!DNL Server\Profiles\Predictive Analytics\Dataset])。 設定 *主伺服器* 並儲存 [!DNL PAServer.cfg] 到實作網站。
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
>本章中的說明不適用於建立 [!DNL Insight Server] 由五(5)個以上 [!DNL Insight Servers]. 請與Adobe聯繫，以獲得超過5個群集的系統要求和配置檔案配置建議 [!DNL Insight Servers].
