---
description: 編輯現有資料集包含檔案的步驟。
title: 編輯現有的資料集包含檔案
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# 編輯現有的資料集包含檔案{#editing-existing-dataset-include-files}

編輯現有資料集包含檔案的步驟。

您可使用Data Workbench中的[!DNL Profile Manager]開啟現有資料集包含檔案。

有關開啟和使用[!DNL Profile Manager]的資訊，請參閱&#x200B;*Data Workbench使用手冊*。

1. 在資料集設定檔中工作時，請開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示目錄內容。

   * 要開啟[!DNL Log Processing Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Log Processing]**&#x200B;以顯示目錄的內容。

   * 要開啟[!DNL Transformation Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Transformation]**&#x200B;以顯示目錄的內容。

1. 以滑鼠右鍵按一下所需資料集包含檔案旁的勾號，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。
1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此時將出現配置窗口。

   您也可以從[!DNL Transformation Dependency Maps]開啟資料集包含檔案。 有關[!DNL Transformation Dependency Maps]的資訊，請參閱[重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

1. 視需要編輯設定檔案中的參數。 如需參數說明，請參閱[記錄處理資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)或[轉換資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 。

   在Data Workbench視窗中編輯資料集包含檔案時，您可以使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、還原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取全部(Ctrl+a)。 此外，還可以使用快捷方式將文本從一個配置檔案([!DNL .cfg])複製並貼到另一個配置檔案。

1. 要保存更改，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。 同步資料集設定檔後，就會開始重新處理或重新轉換資料。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。
