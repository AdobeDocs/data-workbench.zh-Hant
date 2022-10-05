---
description: 資料集目錄包含操作軟體所需的其他檔案，或為Adobe實施提供額外功能。
title: 其他檔案
uuid: 87d83fa5-df25-4da1-8b11-16639902d8d7
exl-id: 0a1fb37c-00ac-46d4-9d0a-904ebd3ccfba
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---

# 其他檔案{#other-files}

{{eol}}

資料集目錄包含操作軟體所需的其他檔案，或為Adobe實施提供額外功能。

* **[!DNL Client.cfg:]** 此 [!DNL Client.cfg] 檔案（位於資料集目錄中） [!DNL Base] 操作軟體時需要配置檔案。 請勿刪除或修改 [!DNL Client.cfg] 檔案。

* **[!DNL Cluster.cfg:]** 此 [!DNL Cluster.cfg] 檔案（位於資料集目錄中） [!DNL Base] 操作軟體時需要配置檔案。 在 [!DNL Cluster.cfg] 檔案中，如果您要設定要在Data Workbench伺服器叢集上處理的資料集，則只應修改「標準化伺服器」參數。 有關修改Normalize Server參數的說明，請參見 [為群集建立集中標準化伺服器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md).

* **[!DNL Insight Transform.cfg]和 [!DNL Insight Transform Mode.cfg]:** 如果您使用轉換功能，則另外有兩個組態檔：data workbench [!DNL Transform.cfg] 和data workbench [!DNL TransformMode.cfg]，位於 [!DNL Transform] 設定檔。 如需這些檔案及其參數的相關資訊，請參閱 [轉換功能](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

* 此 **PAServer.cfg** 檔案。 如果您想要將Predictive Analytics叢集作業提交至Insight Server，則需要設定 [!DNL PAServer.cfg] 處理伺服器端叢集提交的檔案。
自訂設定檔應繼承 [!DNL PAServer.cfg] 來自預測分析設定檔( [!DNL Server\Profiles\Predictive Analytics\Dataset])。

   >[!IMPORTANT]
   >
   >設定 *主伺服器* 並儲存 [!DNL PAServer.cfg] 到實作網站。
   >
   >
   ```
   >PAServer = PAServerConfig: 
   >   Master Server = serverInfo: 
   >       Address = string: 
   >       Port = int: 80
   >       Use SSL = bool: false
   >```
