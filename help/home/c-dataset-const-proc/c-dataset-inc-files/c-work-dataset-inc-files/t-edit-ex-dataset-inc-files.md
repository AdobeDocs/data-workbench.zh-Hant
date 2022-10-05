---
description: 編輯現有資料集包含檔案的步驟。
title: 編輯現有的資料集包含檔案
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# 編輯現有的資料集包含檔案{#editing-existing-dataset-include-files}

{{eol}}

編輯現有資料集包含檔案的步驟。

您可以使用 [!DNL Profile Manager] 在data workbench中。

如需開啟和使用的相關資訊 [!DNL Profile Manager]，請參閱 *Data Workbench使用手冊*.

1. 使用資料集設定檔時，請開啟 [!DNL Profile Manager] 按一下 **[!UICONTROL Dataset]** 顯示目錄的內容。

   * 若要開啟 [!DNL Log Processing Dataset Include] 檔案，按一下 **[!UICONTROL Log Processing]** 顯示目錄的內容。

   * 若要開啟 [!DNL Transformation Dataset Include] 檔案，按一下 **[!UICONTROL Transformation]** 顯示目錄的內容。

1. 以滑鼠右鍵按一下所需資料集包含檔案旁的核取記號，然後按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 此時將出現配置窗口。

   您也可以從 [!DNL Transformation Dependency Maps]. 如需有關 [!DNL Transformation Dependency Maps]，請參閱 [重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. 視需要編輯設定檔案中的參數。 請參閱 [記錄處理資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) 或 [轉換資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 以取得參數的說明。

   在Data Workbench視窗中編輯資料集包含檔案時，您可以使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、還原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取全部(Ctrl+a)。 此外，您可以使用捷徑來複製和貼上來自一個設定檔案的文字( [!DNL .cfg])到其他。

1. 若要儲存變更，請按一下滑鼠右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.
1. 若要讓本機所做的變更生效，請在 [!DNL Profile Manager]，請在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*，其中profile name是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔的名稱。 同步資料集設定檔後，就會開始重新處理或重新轉換資料。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。
