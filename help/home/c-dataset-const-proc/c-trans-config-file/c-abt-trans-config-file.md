---
description: Transformation.cfg檔案可控制資料集建構的轉換階段，在此期間，會將其他資料轉換套用至記錄處理期間已處理的資料，以建立擴充維度以用於分析。
title: 關於轉換組態檔
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# 關於轉換組態檔{#about-the-transformation-configuration-file}

{{eol}}

Transformation.cfg檔案可控制資料集建構的轉換階段，在此期間，會將其他資料轉換套用至記錄處理期間已處理的資料，以建立擴充維度以用於分析。

您必須編輯 [!DNL Transformation.cfg] 檔案，以執行下列任何資料集設定任務：

* 定義 [!DNL log entry condition] 轉換。
* 設定用於建立時間維度和進行時間轉換的時區。 請參閱 [時區](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956).

>[!NOTE]
>
>[!DNL Transformation Dataset Include] 檔案可包含資料集建構轉換階段的其他指示。 這些檔案存在於任何繼承的配置檔案的Dataset\Transformation目錄中，並且通常定義應用程式特定的參數(如 [!DNL Site] 應用程式)。 如需有關 [!DNL Transformation Dataset Include] 檔案，請參閱 [資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md). 如需Site的Web專屬設定參數相關資訊，請參閱 [Web資料的組態設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).
