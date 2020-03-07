---
description: 您隨Adobe應用程式收到的許多內部設定檔都隨附其專屬的資料集設定檔。
solution: Analytics
title: 關於資料集包含檔案
topic: Data workbench
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關於資料集包含檔案{#about-dataset-include-files}

您隨Adobe應用程式收到的許多內部設定檔都隨附其專屬的資料集設定檔。

由於內部配置檔案是資料集配置檔案的子配置檔案，因此其資料集配置檔案包含規則，這些規則為資料集構建的日誌處理或轉換階段提供附加參數。 內部設定檔和您建立之任何繼承設定檔的資料集設定檔稱為資料集包含檔案。

資料集包括檔案包含資料集配置檔案的主資料集配置檔案（或）中包含 [!DNL Log Processing.cfg] 的參 [!DNL Transformation.cfg]數的子集。 資料集包含包含與記錄處理相關的參數的檔案稱為檔案 [!DNL Log Processing Dataset Include] (請參閱「記錄處理資料集包含檔案 [」)，而資料集包含與轉換相關的檔案稱為「檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)[!DNL Transformation Dataset Include] 」。 請參 [閱轉換資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。 您可以建立多個資料集包含檔案，以便用於資料集建構程式。 完整的資料集包含所有資料集設定檔和任何繼承的資料集設定檔中所定義的欄位、轉換和擴充維度。
