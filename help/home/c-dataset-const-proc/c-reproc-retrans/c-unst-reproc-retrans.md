---
description: 在重新處理期間，資料工作台伺服器會依照您在記錄處理和轉換資料集設定檔案中指定的方式重新建構資料集。
title: 瞭解重新處理和重新轉換
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# 瞭解重新處理和重新轉換{#understanding-reprocessing-and-retransformation}

在重新處理期間，資料工作台伺服器會依照您在記錄處理和轉換資料集設定檔案中指定的方式重新建構資料集。

為此，資料工作台伺服器(InsightServer64.exe)必須同時完成資料集建構的記錄處理階段和轉換階段。 日誌處理完成後，它會觸發自動進行轉換，但轉換也可以獨立於日誌處理進行。

在記錄處理階段，資料工作台使用者無法存取資料集中的資料。 在轉換階段，資料工作台使用者確實可以存取最新的資料，但是資料會取樣而非完成。 在轉換期間，資料分析仍可繼續，但查詢的完成速度只有轉換發生的速度一樣快。

## 正在重新處理{#section-92f1e46bf1534b3dba39e9493190b8ab}

每次您完成下列任務之一時，記錄處理以及因此進行的轉換都會自動進行，以重構您的資料集，如您在資料集設定檔案中所指定：

* 新增資料來源。
* 在[!DNL Profile.cfg]檔案中新增資料工作台伺服器至叢集。
* 更改[!DNL Cluster.cfg]檔案。
* 變更[!DNL Log Processing.cfg]檔案或[!DNL Log Processing Dataset Include]檔案，包括但不限於下列項目：

   * 新增參數
   * 變更變形
   * 更改開始時間或結束時間參數

* 升級您的[!DNL Insight Server.exe]檔案。

您也可以隨時在[!DNL Log Processing.cfg]檔案的「重新處理」參數中輸入任何字元或字元組合，並儲存檔案，以開始重新處理。

>[!NOTE]
>
>若要重新處理，[!DNL Log Processing Mode.cfg]檔案中的Pause參數必須設為false。 此參數的預設值為false，因此可能不需要變更參數。 有關[!DNL Log Processing Mode.cfg]的詳細資訊，請參閱[其他配置檔案](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)。

## 重新轉換{#section-02446744549940ada8eba0573ec5575f}

每次更改[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中的任何資訊（如更改轉換或定義新維）時，都會自動進行轉換。

每次更改[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中引用的查找檔案（包括[!DNL Categorize]、[!DNL FlatFileLookup]和[!DNL ODBCLookup]轉換的查找檔案）時，必須在[!DNL Transformation.cfg]檔案的「重新處理」參數中輸入任何字元或字元組合併保存檔案，以啟動轉換。
