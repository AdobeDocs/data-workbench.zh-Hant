---
description: 您可以定義要在資料集建構的記錄處理或轉換階段期間套用的資料轉換。
title: 定義轉換
uuid: 69dd667b-e465-4c1a-a20e-4384e8988cd0
exl-id: 61ce8093-9e64-419a-bddc-dc2225c0eaab
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# 定義轉換{#defining-a-transformation}

您可以定義要在資料集建構的記錄處理或轉換階段期間套用的資料轉換。

>[!NOTE]
>
>Adobe建議在[!DNL Log Processing]或[!DNL Transformation Dataset Include]檔案中定義轉換，而不是在[!DNL Log Processing.cfg]或[!DNL Transformation.cfg]中定義。

只有在[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案中定義了以下轉換後，以下轉換才能工作：

* [](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-appenduri.md#concept-a0df05dd958645bf8219fc7b0b675ee4)AppendURI
* [CrossRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2)
* [LookupRows](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-lookuprows.md#concept-4bd9a1f13ee243e592a6a0008053134f)
* [ODBC 資料來源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)
* [Sessionize](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-sessionize.md#concept-b1af95c8cba34b248f86de883d914bc0)

**定義轉換**

1. 使用[!DNL Profile Manager]開啟要定義轉換的資料集組態檔。

   * （建議）若要開啟資料集包含檔案，請參閱[資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。
   * 要開啟[!DNL Log Processing.cfg]檔案，請參閱[編輯日誌處理配置檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

   * 要開啟[!DNL Transformation.cfg]檔案，請參閱[編輯轉換配置檔案](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

1. 按一下右鍵&#x200B;**[!UICONTROL Transformations]**，然後按一下&#x200B;**[!UICONTROL Add new]** > *&lt;**[!UICONTROL Transformation type]**>*。
1. 輸入轉換的適當資訊。 有關轉換類型的說明及其參數的資訊，請參閱以下各節：

   * [標準轉換](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-standard-transf.md#concept-25f4bdbf8fe74c4aaeb2fcd226243886)
   * [URI 轉換](../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-uri-transf/c-uri-transf.md#concept-2dfa0ffcd83d4fb69c1f42ad50dea125)
   * [整合查閱資料](../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-int-lookup-data.md#concept-08ff70769a464f50ab14299a344f05c7)

1. 在設定檔案中定義轉換後，請將檔案儲存在本機，然後儲存至Data Workbench伺服器上的資料集設定檔。

       定義和編輯轉換的提示：
   
   * 在Data Workbench視窗中編輯轉換的設定時，您可以使用快速鍵來編輯基本的功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、還原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取全部(Ctrl+a)。 此外，還可以使用快捷方式將文本或整個轉換定義從一個配置檔案([!DNL .cfg])複製和貼上到另一個配置檔案。
   * 對於您定義的任何轉換，可以在「注釋」參數中添加一個或多個注釋行，以進一步說明轉換或添加有關其使用的注釋。 若要使用Data Workbench新增註解，請以滑鼠右鍵按一下&#x200B;**[!UICONTROL Comments]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**。

   * 可以從[!DNL Transformation Dependency Map]開啟任何轉換的配置。 開啟設定後，您可以加以編輯並儲存變更。 如需[!DNL Transformation Dependency Maps]的相關資訊，請參閱[資料集組態工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

   * 轉換的空字串輸出可覆寫輸出欄位中的非空字串。
