---
description: 編輯現有資料集的步驟包括檔案。
solution: Analytics
title: 編輯現有資料集包含檔案
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 編輯現有資料集包含檔案{#editing-existing-dataset-include-files}

編輯現有資料集的步驟包括檔案。

您可使用「資料工作台中」開啟現有的資料集 [!DNL Profile Manager] 包含檔案。

如需開啟和使用的詳細資訊 [!DNL Profile Manager]，請參閱資 *料工作台使用指南*。

1. 在資料集設定檔中工作時，開 [!DNL Profile Manager] 啟並按 **[!UICONTROL Dataset]** 一下以顯示目錄的內容。

   * 要開啟文 [!DNL Log Processing Dataset Include] 件，請單 **[!UICONTROL Log Processing]** 擊以顯示目錄的內容。

   * 要開啟文 [!DNL Transformation Dataset Include] 件，請單 **[!UICONTROL Transformation]** 擊以顯示目錄的內容。

1. 以滑鼠右鍵按一下所要的資料集包含檔案旁的核取標籤，然後按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 出現配置窗口。

   您也可以從開啟資料集包含檔案 [!DNL Transformation Dependency Maps]。 如需相關資訊， [!DNL Transformation Dependency Maps]請參閱重新 [處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

1. 視需要編輯配置檔案中的參數。 如需 [參數的說明，請參閱「記錄處理資料集](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) Include Files」(包 [含檔案)或「轉換資料集Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 」（包含檔案）。

   在資料工作台視窗中編輯資料集包含檔案時，您可以使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取所有(Ctrl+a)。 此外，您也可以使用捷徑，將一個設定檔()的文字複製並貼到另 [!DNL .cfg]一個設定檔。

1. 要保存更改，請按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save]**。
1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。 重新處理或重新轉換資料是在同步資料集描述檔後開始。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

