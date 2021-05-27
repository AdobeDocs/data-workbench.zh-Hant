---
description: 設定資料集時，您可以定義變數（以參數形式參照）以表示有意義的值。
title: 定義資料集包含檔案中的參數
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# 定義資料集包含檔案中的參數{#defining-parameters-in-dataset-include-files}

設定資料集時，您可以定義變數（以參數形式參照）以表示有意義的值。

若要為參數指派值（即定義參數），請在記錄處理或[!DNL Transformation Dataset Include]檔案中，將參數的名稱和值新增至「參數」向量。 定義參數後，即可在資料集設定檔的設定檔中參照參數。 定義和參考這些參數稱為參數替代。 在設定資料集時使用參數替代可讓您為參數定義建立集中位置。 當您需要更新多次參照或在多個檔案中參照的參數時，只需變更一次。

>[!NOTE]
>
>在本指南中，術語參數已用於引用配置檔案中任何設定的名稱（如日誌條目條件、重新處理或轉換）。 不過，如本節所用，參數是指資料集包含檔案中「參數」向量的成員，而非配置檔案中設定的名稱。

定義參數時，應考慮下列幾點：

* 參數只能定義一次。 因此，您無法在多個資料集包含檔案中定義相同的變數。
* 您定義的任何參數都是記錄處理或轉換階段的本機參數，但該階段在多個資料集組態檔中是全域的。 例如，如果在[!DNL Transformation Dataset Include]檔案中定義參數，則為整個轉換階段定義參數，並可在[!DNL Transformation.cfg]檔案和繼承的配置檔案的所有其他[!DNL Transformation Dataset Include]檔案中引用該參數。 無法為記錄處理定義參數；因此，對[!DNL Log Processing.cfg]檔案或[!DNL Log Processing Dataset Include]檔案中參數的任何引用都將產生處理錯誤。

**要定義參數**

您可以在[!DNL Log Processing]和[!DNL Transformation Include]檔案中定義字串、數值和向量參數。

1. 在[!DNL Log Processing]或[!DNL Transformation Dataset Include]檔案的Data Workbench視窗中，以滑鼠右鍵按一下&#x200B;**[!UICONTROL Parameters]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Parameter]**。

1. 選擇&#x200B;**[!UICONTROL String Parameter]**、**[!UICONTROL Numeric Parameter]**&#x200B;或&#x200B;**[!UICONTROL Vector Parameter]**，然後按照以下各節所述完成Name和Value參數。

1. 若要儲存您已定義參數的資料集包含檔案，請以滑鼠右鍵按一下視窗頂端的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中檔案的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]***，其中，設定檔名稱是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔。

>[!NOTE]
>
>請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

**參考參數**

* 參考其他資料集組態檔中已定義的參數時，必須將其名稱輸入[!DNL $(parameter name)]。

以下幾節將說明可定義的參數類型。

* [字串與數值參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [向量參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
