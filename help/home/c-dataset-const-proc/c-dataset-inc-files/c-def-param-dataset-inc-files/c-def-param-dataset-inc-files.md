---
description: 在設定資料集時，您可以定義變數（稱為參數）以表示有意義的值。
solution: Analytics
title: 在資料集中定義參數包括檔案
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 在資料集中定義參數包括檔案{#defining-parameters-in-dataset-include-files}

在設定資料集時，您可以定義變數（稱為參數）以表示有意義的值。

要為參數指定值（即，定義參數），可在日誌處理或檔案中將參數的名稱和值添加到「參數」向量 [!DNL Transformation Dataset Include] 中。 定義參數後，可以在資料集配置檔案的配置檔案中引用這些參數。 定義和引用這些參數稱為參數替代。 在設定資料集時使用參數替代可讓您建立參數定義的集中位置。 當您需要更新多次或多個檔案中參考的參數時，您只需變更一次。

>[!NOTE]
>
>在本指南中，術語參數用於引用配置檔案中任何設定的名稱（如日誌條目條件、重新處理或轉換）。 但是，如本節所用，參數會特別引用資料集中「參數」向量的成員，而非設定檔中設定的名稱。

定義參數時應考慮以下幾點：

* 參數必須正確定義一次。 因此，您無法在多個資料集包含檔案中定義相同的變數。
* 您定義的任何參數都是日誌處理或轉換階段的本地參數，但是該階段的參數是跨多個資料集配置檔案的全局參數。 例如，如果在檔案中定義參數，則該參數將為整個轉換階段定義，並且可以在檔案和繼承的配置檔案中引用該參數，以及所有其 [!DNL Transformation Dataset Include][!DNL Transformation.cfg][!DNL Transformation Dataset Include] 它檔案中的參照。 不會為日誌處理定義參數；因此，對檔案或檔案中參數的 [!DNL Log Processing.cfg] 任何引用都 [!DNL Log Processing Dataset Include] 會生成處理錯誤。

**要定義參數，請執行以下操作：**

您可以在和檔案中定義字串、數值和 [!DNL Log Processing] 向量 [!DNL Transformation Include] 參數。

1. 在或檔案的資料工作台 [!DNL Log Processing] 視窗 [!DNL Transformation Dataset Include] 中，以滑鼠右鍵按 **[!UICONTROL Parameters]**&#x200B;一下，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**。

1. 選 **[!UICONTROL String Parameter]**&#x200B;擇、 **[!UICONTROL Numeric Parameter]**&#x200B;或 **[!UICONTROL Vector Parameter]**，並完成「名稱」(Name)和「值」(Value)參數，如以下各節所述。

1. 若要儲存您已定義參數的資料集包含檔案，請在視窗頂端按一 **[!UICONTROL (modified)]** 下滑鼠右鍵並按一下 **[!UICONTROL Save]**。

1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下該檔案的核取標籤，然後按一下 [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***，其中描述檔名稱是資料集描述檔的名稱或資料集包含檔案所屬的繼承描述檔。

>[!NOTE]
>
>請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

**參照參數**

* 在另一個資料集配置檔案中引用定義的參數時，必須將其名稱鍵入 [!DNL $(parameter name)]。

以下各節介紹了可定義的參數類型。

* [字串與數值參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [向量參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

