---
description: 建立新資料集的步驟包括檔案。
solution: Analytics
title: 建立新資料集包含檔案
topic: Data workbench
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 建立新資料集包含檔案{#creating-new-dataset-include-files}

建立新資料集的步驟包括檔案。

您應建立新的資料集包含檔案，以執行以下任何資料集配置任務：

* 指定要從日誌處理傳遞到轉換的新資料欄位。
* 定義執行下列任一操作的轉換：

   * 更新現有的記錄欄位。
   * 產生要從記錄處理傳遞至轉換或用來定義延伸維度的新欄位。

      有關可用轉換類型的資訊，請參 [閱資料轉換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

      >[!NOTE]
      >
      >如果您要定義新資料集包含檔案中的轉換，請務必記住輸入和輸出的順序。 有關轉換順序的資訊，請參 [閱構造轉換慣例](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6)。

* 建立延伸尺寸。 有關可用維類型的資訊，請參閱擴 [展維](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

1. 在資料集設定檔中工作時，開啟並按一 [!DNL Profile Manager] 下以檢 **[!UICONTROL Dataset]** 視現有的資料集包含檔案。

   * 要查看文 [!DNL Log Processing Dataset Include] 件，請按一下 **[!UICONTROL Log Processing]**。

   * 要查看文 [!DNL Transformation Dataset Include] 件，請按一下 **[!UICONTROL Transformation]**。

1. 執行下列 [!DNL Log Processing] 步驟 [!DNL Transformation Dataset Include] 之一，建立新檔案：

   * 在「記錄 [!DNL User] 處理」目錄的欄中，按一下 **[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**。 目錄中將 [!DNL New Log Processing.cfg] 顯示一個名為的檔案。

   * 在「轉 [!DNL User] 換」目錄的列中，按一下 **[!UICONTROL Create]** > **[!UICONTROL New Transformation]**。 目錄中將 [!DNL New Transformation.cfg] 顯示一個名為的檔案。

1. 在列中按一下右鍵新檔案的複選標籤，並在「檔案」 [!DNL User] 參數中鍵入新名稱，以更名該新檔案。

   ![步驟資訊](assets/vis_ProfileManager_RenameFile.png)

1. 按一下右鍵更名檔案的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現配置窗口。
1. 視需要編輯配置檔案中的參數。 如需 [可用參數的說明，請參閱「記錄處理資料集包括檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) 」 [](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) 或「轉換資料集包括檔案」。
1. 要保存更改，請按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save]**。
1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。 重新處理或重新轉換資料是在同步資料集描述檔後開始。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

若要編輯您建立的資料集包含檔案，請參閱編輯 [現有資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。
