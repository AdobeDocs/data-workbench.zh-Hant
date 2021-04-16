---
description: 建立新資料集的步驟包括檔案。
title: 建立新的資料集包含檔案
uuid: 707bdd84-b12b-4226-b6aa-43c9fc7ec9fe
exl-id: 8a7b343d-b695-41aa-b465-8c5cd68d6ef7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 3%

---

# 建立新的資料集包含檔案{#creating-new-dataset-include-files}

建立新資料集的步驟包括檔案。

您應建立新的資料集包含檔案，以執行以下任何資料集配置任務：

* 指定要從日誌處理傳遞到轉換的新資料欄位。
* 定義執行下列任一操作的轉換：

   * 更新現有的記錄欄位。
   * 產生要從記錄處理傳遞至轉換或用來定義延伸維度的新欄位。

      有關可用轉換類型的資訊，請參閱[資料轉換](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

      >[!NOTE]
      >
      >如果您要定義新資料集包含檔案中的轉換，請務必記住輸入和輸出的順序。 有關轉換順序的資訊，請參見[構造轉換的約定](../../../../home/c-dataset-const-proc/c-data-trans/c-con-transf.md#concept-01998eebb7e347c58255fb442f2613b6)。

* 建立延伸尺寸。 有關可用維類型的資訊，請參閱[擴展Dimension](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

1. 在您的資料集設定檔中工作時，開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以檢視現有的資料集包含檔案。

   * 要查看[!DNL Log Processing Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Log Processing]**。

   * 要查看[!DNL Transformation Dataset Include]檔案，請按一下&#x200B;**[!UICONTROL Transformation]**。

1. 執行下列步驟之一，建立新的[!DNL Log Processing]或[!DNL Transformation Dataset Include]檔案：

   * 在日誌處理目錄的[!DNL User]列中，按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL New Log Processing]**。 目錄中將顯示一個名為[!DNL New Log Processing.cfg]的檔案。

   * 在「轉換」目錄的[!DNL User]列中，按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL New Transformation]**。 目錄中將顯示一個名為[!DNL New Transformation.cfg]的檔案。

1. 在[!DNL User]欄中按一下右鍵新檔案的複選標籤，然後在「檔案」參數中鍵入新名稱，以更名該新檔案。

   ![步驟資訊](assets/vis_ProfileManager_RenameFile.png)

1. 按一下右鍵更名檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現配置窗口。
1. 視需要編輯配置檔案中的參數。 有關可用參數的說明，請參閱[日誌處理資料集包括檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)或[轉換資料集包括檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace)。
1. 要保存更改，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。 重新處理或重新轉換資料是在同步資料集描述檔後開始。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

要編輯包含您建立的檔案的資料集，請參閱[編輯現有資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。
