---
description: 編輯現有資料集的步驟包括檔案。
title: 編輯現有的資料集包含檔案
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# 編輯現有的資料集包含檔案{#editing-existing-dataset-include-files}

編輯現有資料集的步驟包括檔案。

在資料工作台中，您使用[!DNL Profile Manager]開啟現有的資料集包含檔案。

有關開啟和使用[!DNL Profile Manager]的資訊，請參閱&#x200B;*Data Workbench使用手冊*。

1. 在資料集配置檔案中工作時，開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示目錄的內容。

   * 要開啟[!DNL Log Processing Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Log Processing]**&#x200B;以顯示目錄的內容。

   * 要開啟[!DNL Transformation Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Transformation]**&#x200B;以顯示目錄的內容。

1. 在所需資料集包含檔案旁的核取標籤上按一下滑鼠右鍵，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。
1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現配置窗口。

   您也可以從[!DNL Transformation Dependency Maps]開啟資料集包含檔案。 有關[!DNL Transformation Dependency Maps]的資訊，請參閱[重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

1. 視需要編輯配置檔案中的參數。 有關參數的說明，請參閱[日誌處理資料集包括檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)或[轉換資料集包括檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。

   在資料工作台視窗中編輯資料集包含檔案時，您可以使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取所有(Ctrl+a)。 此外，您還可以使用捷徑，將一個設定檔案([!DNL .cfg])的文字複製並貼到另一個設定檔。

1. 要保存更改，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。 重新處理或重新轉換資料是在同步資料集描述檔後開始。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。
