---
description: 在設定資料集時，您可以定義變數（稱為參數）以表示有意義的值。
title: 定義資料集包含檔案中的參數
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# 定義資料集包含檔案中的參數{#defining-parameters-in-dataset-include-files}

在設定資料集時，您可以定義變數（稱為參數）以表示有意義的值。

要為參數指定值（即，定義參數），可在日誌處理或[!DNL Transformation Dataset Include]檔案中將參數的名稱和值添加到「參數」向量。 定義參數後，可以在資料集配置檔案的配置檔案中引用這些參數。 定義和引用這些參數稱為參數替代。 在設定資料集時使用參數替代可讓您建立參數定義的集中位置。 當您需要更新多次或多個檔案中參考的參數時，您只需變更一次。

>[!NOTE]
>
>在本指南中，術語參數用於引用配置檔案中任何設定的名稱（如日誌條目條件、重新處理或轉換）。 但是，如本節所用，參數會特別引用資料集中「參數」向量的成員，而非設定檔中設定的名稱。

定義參數時應考慮以下幾點：

* 參數必須正確定義一次。 因此，您無法在多個資料集包含檔案中定義相同的變數。
* 您定義的任何參數都是日誌處理或轉換階段的本地參數，但是該階段的參數是跨多個資料集配置檔案的全局參數。 例如，如果在[!DNL Transformation Dataset Include]檔案中定義參數，則該參數將為整個轉換階段定義，並且可以在[!DNL Transformation.cfg]檔案和所有其它[!DNL Transformation Dataset Include]檔案中引用該參數，以用於繼承的配置檔案。 不會為日誌處理定義參數；因此，對[!DNL Log Processing.cfg]檔案或[!DNL Log Processing Dataset Include]檔案中參數的任何參照都會產生處理錯誤。

**要定義參數，請執行以下操作：**

您可以在[!DNL Log Processing]和[!DNL Transformation Include]檔案中定義字串、數值和向量參數。

1. 在[!DNL Log Processing]或[!DNL Transformation Dataset Include]檔案的資料工作台視窗中，以滑鼠右鍵按一下&#x200B;**[!UICONTROL Parameters]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Parameter]**。

1. 選擇&#x200B;**[!UICONTROL String Parameter]**、**[!UICONTROL Numeric Parameter]**&#x200B;或&#x200B;**[!UICONTROL Vector Parameter]**，然後按照以下各節所述完成「名稱」和「值」參數。

1. 要保存已定義參數的資料集包含檔案，請按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>* ，其中配置檔案名稱是資料集配置檔案的名稱或資料集包含檔案所屬的繼承配置檔案。

>[!NOTE]
>
>請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。

**參照參數**

* 當在另一個資料集配置檔案中引用定義的參數時，必須將其名稱鍵入[!DNL $(parameter name)]。

以下各節介紹了可定義的參數類型。

* [字串與數值參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [向量參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
