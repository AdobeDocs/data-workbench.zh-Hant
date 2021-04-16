---
description: Transformation.cfg檔案控制資料集建構的轉換階段，在此階段，額外的資料轉換會套用至記錄處理期間已處理的資料，以建立擴充維度以供分析使用。
title: 關於轉換組態檔
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
exl-id: 860562d7-6ed3-486b-9f62-1bd06878bf7e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 5%

---

# 關於轉換組態檔{#about-the-transformation-configuration-file}

Transformation.cfg檔案控制資料集建構的轉換階段，在此階段，額外的資料轉換會套用至記錄處理期間已處理的資料，以建立擴充維度以供分析使用。

您必須編輯[!DNL Transformation.cfg]檔案，才能執行下列任何資料集設定工作：

* 定義轉換的[!DNL log entry condition]，從日誌處理中過濾資料。
* 設定用於建立時間維度和進行時間轉換的時區。 請參閱[時區](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956)。

>[!NOTE]
>
>[!DNL Transformation Dataset Include] 檔案可以包含資料集構建的轉換階段的附加說明。這些檔案存在於任何繼承的配置檔案的Dataset\Transformation目錄中，它們通常定義特定於應用程式的參數（如[!DNL Site]應用程式的Web特定配置參數）。 有關[!DNL Transformation Dataset Include]檔案的資訊，請參見[資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。 如需網站特定Web組態參數的詳細資訊，請參閱[網站資料的組態設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。
