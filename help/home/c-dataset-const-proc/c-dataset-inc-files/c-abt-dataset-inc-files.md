---
description: 您收到的許多Adobe應用程式內部設定檔都會隨附自己的資料集組態檔。
title: 關於資料集包含檔案
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 4%

---

# 關於資料集包含檔案{#about-dataset-include-files}

{{eol}}

您收到的許多Adobe應用程式內部設定檔都會隨附自己的資料集組態檔。

由於內部設定檔是資料集設定檔的子設定檔，因此其資料集組態檔包含的規則會為資料集建構的記錄處理或轉換階段提供額外參數。 內部設定檔和您建立之任何繼承設定檔的資料集組態檔，稱為資料集包含檔案。

資料集包含檔案包含主要資料集組態檔所包含參數的子集( [!DNL Log Processing.cfg] 或 [!DNL Transformation.cfg])（適用於資料集設定檔）。 系統會呼叫包含與記錄處理相關聯之參數的資料集包含檔案 [!DNL Log Processing Dataset Include] 檔案(請參閱 [記錄處理資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab))，則會呼叫與轉換相關聯的資料集包含檔案 [!DNL Transformation Dataset Include] 檔案。 請參閱 [轉換資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). 您可以建立多個資料集包含檔案，以用於資料集建構程式。 完整資料集包含所有欄位、轉換，以及在資料集設定檔和任何繼承設定檔的所有資料集組態檔中定義的延伸維度。
