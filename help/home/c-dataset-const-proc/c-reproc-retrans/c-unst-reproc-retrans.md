---
description: 在重新處理期間，資料工作台伺服器會依照您在記錄處理和轉換資料集設定檔案中指定的方式重新建構資料集。
solution: Analytics
title: 瞭解重新處理和重新轉換
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 瞭解重新處理和重新轉換{#understanding-reprocessing-and-retransformation}

在重新處理期間，資料工作台伺服器會依照您在記錄處理和轉換資料集設定檔案中指定的方式重新建構資料集。

為此，資料工作台伺服器(InsightServer64.exe)必須同時完成資料集建構的記錄處理階段和轉換階段。 日誌處理完成後，它會觸發自動進行轉換，但轉換也可以獨立於日誌處理進行。

在記錄處理階段，資料工作台使用者無法存取資料集中的資料。 在轉換階段，資料工作台使用者確實可以存取最新的資料，但是資料會取樣而非完成。 在轉換期間，資料分析仍可繼續，但查詢的完成速度只有轉換發生的速度一樣快。

## 重新處理 {#section-92f1e46bf1534b3dba39e9493190b8ab}

每次您完成下列任務之一時，記錄處理以及因此進行的轉換都會自動進行，以重構您的資料集，如您在資料集設定檔案中所指定：

* 新增資料來源。
* 在檔案中新增資料工作台伺服器至叢集 [!DNL Profile.cfg] 中。
* 變更檔 [!DNL Cluster.cfg] 案。
* 變更檔 [!DNL Log Processing.cfg] 案或檔 [!DNL Log Processing Dataset Include] 案，包括但不限於：

   * 新增參數
   * 變更變形
   * 更改開始時間或結束時間參數

* 升級您的 [!DNL Insight Server.exe] 檔案。

您也可以隨時在檔案的「重新處理」參數中輸入任何字元或字元組合，並儲 [!DNL Log Processing.cfg] 存檔案，以開始重新處理。

>[!NOTE]
>
>若要重新處理，檔案中的「暫停」 [!DNL Log Processing Mode.cfg] 參數必須設為false。 此參數的預設值為false，因此可能不需要更改參數。 如需詳細資訊，請 [!DNL Log Processing Mode.cfg]參閱其 [他設定檔](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md)。

## 再變形 {#section-02446744549940ada8eba0573ec5575f}

每次更改檔案或檔案中的 [!DNL Transformation.cfg] 任何資訊( [!DNL Transformation Dataset Include] 如更改變形或定義新尺寸)時，都會自動進行轉換。

每次更改檔案或檔案(包括 [!DNL Transformation.cfg] 、 [!DNL Transformation Dataset Include] 、和 [!DNL Categorize]轉換的查閱檔案)中引用的查閱檔案時，必須通過在檔案的「重新處理」參數中輸入任何字元或字元組合併保存檔案來啟動 [!DNL FlatFileLookup][!DNL ODBCLookup][!DNL Transformation.cfg] 轉換。
