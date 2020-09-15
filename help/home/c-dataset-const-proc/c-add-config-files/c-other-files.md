---
description: 「資料集」目錄包含執行軟體作業所需的其他檔案，或是為您的Adobe實作提供其他功能。
solution: Analytics
title: 其他檔案
topic: Data workbench
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---


# 其他檔案{#other-files}

「資料集」目錄包含執行軟體作業所需的其他檔案，或是為您的Adobe實作提供其他功能。

* **[!DNL Client.cfg:]** 對於 [!DNL Client.cfg] 軟體的操作，需要在Dataset目錄 [!DNL Base] 中的配置檔案。 請勿刪除或修改檔案中的任何 [!DNL Client.cfg] 參數。

* **[!DNL Cluster.cfg:]** 對於 [!DNL Cluster.cfg] 軟體的操作，需要在Dataset目錄 [!DNL Base] 中的配置檔案。 在檔案 [!DNL Cluster.cfg] 中，如果您要設定資料集以便在資料工作台伺服器叢集上處理，則只應修改Normalize Server參數。 有關修改標準化伺服器參數的說明，請參 [閱為群集建立集中式標準化伺服器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

* **[!DNL Insight Transform.cfg]和[!DNL Insight Transform Mode.cfg]:** 如果您使用轉換功能，則配置檔案的「資料集」目錄中還有兩 [!DNL Transform.cfg] 個其 [!DNL TransformMode.cfg]他配置檔案：資料工作台和資料工 [!DNL Transform] 作台。 如需這些檔案及其參數的詳細資訊，請參 [閱轉換功能](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)。

* PAServer.cfg **檔案** 。 如果您想要將Predictive Analytics叢集工作提交至Insight Server，則需要設定檔案，以處理 [!DNL PAServer.cfg] 伺服器端叢集提交。
自訂描述檔應繼承 [!DNL PAServer.cfg] Predictive Analytics描述檔( [!DNL Server\Profiles\Predictive Analytics\Dataset])。

   >[!IMPORTANT]
   >
   >在此檔 *案中設定Master Server* ，並將它 [!DNL PAServer.cfg] 儲存至實作網站。
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```

