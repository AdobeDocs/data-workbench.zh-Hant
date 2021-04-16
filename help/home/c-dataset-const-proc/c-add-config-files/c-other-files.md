---
description: 「資料集」目錄包含操作軟體所需的其他檔案，或為您的Adobe實作提供其他功能。
title: 其他檔案
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---

# 其他檔案{#other-files}

「資料集」目錄包含操作軟體所需的其他檔案，或為您的Adobe實作提供其他功能。

* **[!DNL Client.cfg:]** 在 [!DNL Client.cfg] 操作軟體時，需要配置 [!DNL Base] 檔案的Dataset目錄內的檔案。請勿刪除或修改[!DNL Client.cfg]檔案中的任何參數。

* **[!DNL Cluster.cfg:]** 在 [!DNL Cluster.cfg] 操作軟體時，需要配置 [!DNL Base] 檔案的Dataset目錄內的檔案。在[!DNL Cluster.cfg]檔案中，如果您要設定資料集以便在資料工作台伺服器叢集上處理，則只應修改標準化伺服器參數。 有關修改標準化伺服器參數的說明，請參閱[為群集建立集中式標準化伺服器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)。

* **[!DNL Insight Transform.cfg]和 [!DNL Insight Transform Mode.cfg]：如** 果您使用轉換功能，描述檔的「資料集」目錄中會有另外兩 [!DNL Transform.cfg] 個設定檔案：資料工 [!DNL TransformMode.cfg]作台和資料 [!DNL Transform] 工作台。有關這些檔案及其參數的資訊，請參見[轉換功能](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)。

* **PAServer.cfg**&#x200B;檔案。 如果您想要將Predictive Analytics叢集工作提交至Insight Server，則需要設定[!DNL PAServer.cfg]檔案，以處理伺服器端叢集提交。
自訂描述檔應繼承預測性分析描述檔([!DNL Server\Profiles\Predictive Analytics\Dataset])中的[!DNL PAServer.cfg]。

   >[!IMPORTANT]
   >
   >在此檔案中設定&#x200B;*主伺服器*，並將[!DNL PAServer.cfg]保存到實施站點。
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
