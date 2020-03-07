---
description: 當您要處理並讓Insight和Report的使用者存取的資料量超過單一Insight Server的容量時，就需要Insight Server叢集。
solution: Insight
title: 關於Insight Server叢集
uuid: d65e0fe5-f87d-4d8e-a208-9192e9d62fb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關於Insight Server叢集{#about-insight-server-clusters}

當您要處理並讓Insight和Report的使用者存取的資料量超過單一Insight Server的容量時，就需要Insight Server叢集。

設定叢集後，您 [!DNL Insight Server] 就可以在叢集中的多部機器上，分發單一分析資料集，以利用多部機器的處理能力 [!DNL Insight Servers]。

群集實施的第一步是 [!DNL Insight Server] 在群集中分 [!DNL Insight Server] 配電腦。 您設 [!DNL Insight Server] 定的第一台電腦是您的主 [!DNL Insight Server] 版(有時稱為您的主版 [!DNL Insight Server])。

>[!NOTE]
>
>如果您使用檔 [!DNL Insight Server] 案伺服器單元(FSU),Adobe建議您將FSU設為主伺服器 [!DNL Insight Server]。 如需設定FSU的詳細資訊，請參閱資料集 *設定指南*。

主機管 [!DNL Insight Server] 理群集中的其他 [!DNL Insight Servers] （稱為處理伺服器，有時稱為查詢伺服器）與和實例之間的 [!DNL Insight] 通信 [!DNL Report]。 對於給定資料集，日誌檔案處理會在配置檔案中指定的（一個或多個） [!DNL Insight Servers] 指定（主檔案或處理）上 [!DNL Insight Server] 進行。 在群集環境中工作時， [!DNL Insight] 將安裝配置為訪問主機 [!DNL Insight Server]，但查詢可由群集內的任 [!DNL Insight Servers] 何一個處理。

>[!NOTE]
>
>PAServer.cfg **檔案** 。 如果您想要將Predictive Analytics叢集工作提交至Insight Server，則需要設定檔案，以處理 [!DNL PAServer.cfg] 伺服器端叢集提交。 自訂描述檔應繼承 [!DNL PAServer.cfg] Predictive Analytics描述檔( [!DNL Server\Profiles\Predictive Analytics\Dataset])。 在此檔 *案中設定Master Server* ，並將它 [!DNL PAServer.cfg] 儲存至實作網站。>
>
```>
>PAServer = PAServerConfig: 
>   Master Server = serverInfo: 
>       Address = string: 
>       Port = int: 80
>       Use SSL = bool: false
>```>



>[!IMPORTANT]
>
>本章中的說明不適用於建立由五(5) [!DNL Insight Server] 個以上的群集 [!DNL Insight Servers]。 請連絡Adobe，以取得超過5個叢集的系統需求和描述檔設定建議 [!DNL Insight Servers]。

