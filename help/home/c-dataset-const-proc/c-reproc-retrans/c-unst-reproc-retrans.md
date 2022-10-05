---
description: 在重新處理期間，Data Workbench伺服器會依照您在記錄處理和轉換資料集組態檔中所指定的方式，重新建構您的資料集。
title: 瞭解重新處理和重新轉換
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# 瞭解重新處理和重新轉換{#understanding-reprocessing-and-retransformation}

{{eol}}

在重新處理期間，Data Workbench伺服器會依照您在記錄處理和轉換資料集組態檔中所指定的方式，重新建構您的資料集。

若要這麼做，Data Workbench伺服器(InsightServer64.exe)必須同時完成資料集建構的記錄處理階段和轉換階段。 記錄處理完成時，會觸發自動進行轉換，但轉換也可能獨立於記錄處理而發生。

在記錄處理階段期間，Data Workbench使用者無法存取資料集中的資料。 在轉換階段中，Data Workbench使用者確實可存取最新資料，但資料會以取樣而非完成。 轉換期間可以繼續進行資料分析，但查詢只有在轉換發生時盡快完成。

## 重新處理 {#section-92f1e46bf1534b3dba39e9493190b8ab}

每次您完成下列其中一項工作時，記錄處理（因此也會進行轉換）就會自動進行，以依照您在資料集組態檔中指定的方式重新建構資料集：

* 新增資料來源。
* 將新的Data Workbench伺服器新增至 [!DNL Profile.cfg] 檔案。
* 變更 [!DNL Cluster.cfg] 檔案。
* 變更 [!DNL Log Processing.cfg] 檔案或 [!DNL Log Processing Dataset Include] 檔案，包括但不限於下列項目：

   * 新增參數
   * 變更轉換
   * 更改開始時間或結束時間參數

* 升級您的 [!DNL Insight Server.exe] 檔案。

您也可以隨時透過在的「重新處理」參數中輸入任何字元或字元組合，來起始重新處理 [!DNL Log Processing.cfg] 檔案並儲存檔案。

>[!NOTE]
>
>若要重新處理，請在 [!DNL Log Processing Mode.cfg] 檔案必須設為false。 此參數的預設值為false，因此可能不需要變更參數。 如需 [!DNL Log Processing Mode.cfg]，請參閱 [其他組態檔](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## 重新轉換 {#section-02446744549940ada8eba0573ec5575f}

每次您變更 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案（如更改轉換或定義新維）會自動進行轉換。

每次您變更 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案(包括 [!DNL Categorize], [!DNL FlatFileLookup]，和 [!DNL ODBCLookup] 轉換)，您必須通過在的「重新處理」參數中輸入任何字元或字元組合來啟動轉換 [!DNL Transformation.cfg] 檔案並儲存檔案。
