---
description: 資料集目錄包含操作軟體所需的其他檔案，或為Adobe實施提供額外功能。
title: 其他檔案
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# 其他檔案{#other-files}

資料集目錄包含操作軟體所需的其他檔案，或為Adobe實施提供額外功能。

* **[!DNL Client.cfg:]** 操作 [!DNL Client.cfg] 軟體時，需要資料集目 [!DNL Base] 錄內的配置檔案。請勿刪除或修改[!DNL Client.cfg]檔案中的任何參數。

* **[!DNL Cluster.cfg:]** 操作 [!DNL Cluster.cfg] 軟體時，需要資料集目 [!DNL Base] 錄內的配置檔案。在[!DNL Cluster.cfg]檔案中，如果您要設定要在Data Workbench伺服器叢集上處理的資料集，則只應修改「標準化伺服器」參數。 有關修改標準化伺服器參數的說明，請參閱[為群集](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md)建立集中標準化伺服器。

* **[!DNL Insight Transform.cfg]和 [!DNL Insight Transform Mode.cfg]:** 如果您使用轉換功能，設定檔的「資料集」目錄中有另 [!DNL Transform.cfg] 外兩個組態檔： [!DNL TransformMode.cfg] data workbench和 [!DNL Transform] data workbench。有關這些檔案及其參數的資訊，請參閱[轉換功能](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html)。

* **PAServer.cfg**&#x200B;檔案。 如果您想要將Predictive Analytics叢集作業提交至Insight Server，則需要設定[!DNL PAServer.cfg]檔案，以處理伺服器端叢集提交。
自訂設定檔應繼承預測分析設定檔的[!DNL PAServer.cfg]([!DNL Server\Profiles\Predictive Analytics\Dataset])。

   >[!IMPORTANT]
   >
   >在此檔案中設定&#x200B;*主伺服器*&#x200B;並將[!DNL PAServer.cfg]儲存到實作網站。
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
