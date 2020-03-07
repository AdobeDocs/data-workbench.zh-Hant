---
description: Transformation.cfg檔案控制資料集建構的轉換階段，在此階段，額外的資料轉換會套用至記錄處理期間已處理的資料，以建立擴充維度以供分析使用。
solution: Analytics
title: 關於轉換配置檔案
topic: Data workbench
uuid: 56e11b71-1a86-47d4-8d2a-2795532b0770
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 關於轉換配置檔案{#about-the-transformation-configuration-file}

Transformation.cfg檔案控制資料集建構的轉換階段，在此階段，額外的資料轉換會套用至記錄處理期間已處理的資料，以建立擴充維度以供分析使用。

您必須編輯文 [!DNL Transformation.cfg] 件，才能執行下列任何資料集配置任務：

* 定義轉換，從記錄處理中篩選 [!DNL log entry condition] 資料。
* 設定用於建立時間維度和進行時間轉換的時區。 請參 [閱時區](../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956)。

>[!NOTE]
>
>[!DNL Transformation Dataset Include] 檔案可以包含資料集構建的轉換階段的附加說明。 這些檔案存在於任何繼承的配置檔案的Dataset\Transformation目錄中，它們通常定義特定於應用程式的參數(如應用程式的Web特定配置 [!DNL Site] 參數)。 如需檔案的相 [!DNL Transformation Dataset Include] 關資訊，請參 [閱資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。 如需網站特定Web組態參數的詳細資訊，請參閱網 [站資料的組態設定](../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

