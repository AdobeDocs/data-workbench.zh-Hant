---
description: 設定資料集時，您可以定義變數（以參數形式參照）以表示有意義的值。
title: 定義資料集包含檔案中的參數
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 3%

---

# 定義資料集包含檔案中的參數{#defining-parameters-in-dataset-include-files}

{{eol}}

設定資料集時，您可以定義變數（以參數形式參照）以表示有意義的值。

若要為參數指派值（即定義參數），您可在記錄處理或 [!DNL Transformation Dataset Include] 檔案。 定義參數後，即可在資料集設定檔的設定檔中參照參數。 定義和參考這些參數稱為參數替代。 在設定資料集時使用參數替代可讓您為參數定義建立集中位置。 當您需要更新多次參照或在多個檔案中參照的參數時，只需變更一次。

>[!NOTE]
>
>在本指南中，術語參數已用於引用配置檔案中任何設定的名稱（如日誌條目條件、重新處理或轉換）。 不過，如本節所用，參數是指資料集包含檔案中「參數」向量的成員，而非配置檔案中設定的名稱。

定義參數時，應考慮下列幾點：

* 參數只能定義一次。 因此，您無法在多個資料集包含檔案中定義相同的變數。
* 您定義的任何參數都是記錄處理或轉換階段的本機參數，但該階段在多個資料集組態檔中是全域的。 例如，若您在 [!DNL Transformation Dataset Include] 檔案中，該參數是為整個轉換階段定義的，並且可以在 [!DNL Transformation.cfg] 檔案和所有其他 [!DNL Transformation Dataset Include] 檔案。 無法為記錄處理定義參數；因此，在 [!DNL Log Processing.cfg] 檔案或 [!DNL Log Processing Dataset Include] 檔案會產生處理錯誤。

**要定義參數**

您可以在 [!DNL Log Processing] 和 [!DNL Transformation Include] 檔案。

1. 在資料工作台視窗中， [!DNL Log Processing] 或 [!DNL Transformation Dataset Include] 檔案，按一下右鍵 **[!UICONTROL Parameters]**，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**.

1. 選擇 **[!UICONTROL String Parameter]**, **[!UICONTROL Numeric Parameter]**，或 **[!UICONTROL Vector Parameter]**，並依照下列章節所述，完成名稱和值參數。

1. 若要儲存您已定義參數的資料集包含檔案，請按一下滑鼠右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

1. 若要讓本機所做的變更生效，請在 [!DNL Profile Manager]，請在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*，其中profile name是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔的名稱。

>[!NOTE]
>
>請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

**參考參數**

* 參考其他資料集組態檔中已定義的參數時，您必須將其名稱輸入 [!DNL $(parameter name)].

以下幾節將說明可定義的參數類型。

* [字串與數值參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [向量參數](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
