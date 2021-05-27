---
description: 建立新資料集包含檔案的步驟。
title: 建立新的資料集包含檔案
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# 建立新的資料集包含檔案{#creating-new-dataset-include-files}

建立新資料集包含檔案的步驟。

您應建立新的資料集包含檔案，以執行下列任何資料集設定工作：

* 指定要從記錄處理傳遞到轉換的新資料欄位。
* 定義執行下列任一操作的轉換：

   * 更新現有日誌欄位。
   * 產生要從記錄處理傳遞至轉換或用來定義延伸維度的新欄位。

      有關可用轉換類型的資訊，請參閱[資料轉換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

      >[!NOTE]
      >
      >如果您要定義新資料集包含檔案中的轉換，請務必記住輸入和輸出的順序。 有關轉換順序的資訊，請參閱[構造轉換的慣例](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6)。

* 建立延伸維度。 如需可用維度類型的相關資訊，請參閱[延伸Dimension](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

1. 在資料集設定檔中工作時，請開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以檢視現有的資料集包含檔案。

   * 要查看[!DNL Log Processing Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Log Processing]**。

   * 要查看[!DNL Transformation Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Transformation]**。

1. 執行下列步驟之一，建立新的[!DNL Log Processing]或[!DNL Transformation Dataset Include]檔案：

   * 在「記錄處理」目錄的[!DNL User]欄中，按一下「**[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**」。 名為[!DNL New Log Processing.cfg]的檔案將出現在目錄中。

   * 在轉換目錄的[!DNL User]列中，按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL New Transformation]**。 名為[!DNL New Transformation.cfg]的檔案將出現在目錄中。

1. 在[!DNL User]列中按一下右鍵其複選標籤，並在File參數中鍵入新名稱，以更名新檔案。

   ![步驟資訊](assets/vis_ProfileManager_RenameFile.png)

1. 按一下右鍵更名檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此時將出現配置窗口。
1. 視需要編輯設定檔案中的參數。 如需可用參數的說明，請參閱[記錄處理資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)或[轉換資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 。
1. 要保存更改，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。 同步資料集設定檔後，就會開始重新處理或重新轉換資料。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

若要編輯您建立的資料集包含檔案，請參閱[編輯現有的資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。
