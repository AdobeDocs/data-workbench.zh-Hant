---
description: 將記錄檔處理為記錄來源需要定義「記錄處理資料集包含檔案」中的解碼器，以從記錄項目擷取資料欄位。
title: 文字檔案解碼器群組
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
exl-id: e9f6e02e-7150-455f-96f0-f34d98cc31b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# 文字檔案解碼器群組{#text-file-decoder-groups}

{{eol}}

將記錄檔處理為記錄來源需要定義「記錄處理資料集包含檔案」中的解碼器，以從記錄項目擷取資料欄位。

為日誌檔案日誌源定義文本檔案解碼器組需要了解日誌檔案的結構和內容、要提取的資料以及儲存該資料的欄位。 本節提供您可以為解碼器指定之參數的基本說明，但您使用任何解碼器的方式取決於包含來源資料的記錄檔。

有關日誌檔案日誌源的格式要求的資訊，請參見 [記錄檔](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). 如需定義文字檔案解碼器的協助，請聯絡Adobe。

文字檔案解碼器群組可包括：

* [規則運算式解碼器](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [分隔解碼器](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## 規則運算式解碼器 {#section-67aca2c1f008404da7f845a64abec97c}

規則運算式解碼器識別記錄檔中記錄項目內的複雜字串模式，並將這些模式提取為資料欄位。 對於每個解碼器，欄位數必須等於規則運算式中擷取子模式的數量。 將匹配第n捕捉子模式的行的部分分配給該行的第n欄位。

**將規則運算式解碼器新增至文字檔案解碼器群組**

1. 開啟 [!DNL Log Processing Dataset Include] 檔案，如 [編輯現有的資料集包含檔案](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) 並新增文字檔案解碼器群組。 請參閱表格項目 [解碼器群組](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. 按一下右鍵 **[!UICONTROL Decoders]** 在新建立的解碼器群組下，按一下 **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. 指定下列資訊：

   * **欄位：** 記錄檔中的欄位清單。 若要將此處定義的任何欄位傳遞至資料集建構的轉換階段，這些欄位必須列在其中一個欄位的「欄位」參數中 [!DNL Log Processing Dataset Include] 資料集的檔案。 自訂欄位名稱必須以「x — 」開頭。

   * **名稱：** 解碼器的選用識別碼。
   * **規則運算式：** 用於從檔案的每行擷取所需欄位。

1. 對於要添加到組的任何其他解碼器，重複步驟4和5。
1. 若要儲存 [!DNL Log Processing Dataset Include] 檔案，按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

1. 若要讓本機所做的變更生效，請在 [!DNL Profile Manager]，請在 [!DNL User] 欄。 按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*，其中profile name是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔的名稱。

請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

>[!NOTE]
>
>指定的日誌檔案可以具有多個規則表達式解碼器。 定義解碼器的順序非常重要：匹配日誌檔案中行的第一解碼器是用於解碼該行的解碼器。

此範例說明如何使用規則運算式解碼器，從以Tab分隔的文字檔案擷取資料欄位。 您可以定義具有定位分隔字元的分隔解碼器來達到相同的結果。

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

如需規則運算式解碼器的詳細資訊，包括術語和語法，請參閱 [規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## 分隔解碼器 {#section-7e0a23decdbc4c75ae750a42446997a6}

分隔解碼器解碼其欄位由單一字元分隔的記錄檔。 欄位數必須與分隔檔案中的欄數相對應；不過，並非所有欄位都需要命名。 如果欄位留空，記錄檔中仍需要欄位，但解碼器會忽略欄位。

**將分隔解碼器新增至文字檔案解碼器群組**

1. 開啟 [!DNL Log Processing Dataset Include] 檔案，如 [編輯現有的資料集包含檔案](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) 並新增文字檔案解碼器群組。 請參閱表格項目 [解碼器群組](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. 按一下右鍵 **[!UICONTROL Decoders]** 在新建立的解碼器群組下，按一下 **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. 指定下列資訊：

   * **欄位：** 記錄檔中的欄位清單。 若要將此處定義的任何欄位傳遞至資料集建構的轉換階段，這些欄位必須列在其中一個欄位的「欄位」參數中 [!DNL Log Processing Dataset Include] 資料集的檔案。 自訂欄位名稱必須以「x — 」開頭。

   * **分隔字元：** 用於分隔輸出檔案中欄位的字元。

1. 對於要添加到組的任何其他解碼器，重複步驟4和5。
1. 若要儲存 [!DNL Log Processing Dataset Include] 檔案，按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

1. 若要讓本機所做的變更生效，請在 [!DNL Profile Manager]，請在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*，其中profile name是資料集設定檔的名稱，或資料集包含檔案所屬的繼承設定檔的名稱。

>[!NOTE]
>
>請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

此範例說明如何使用分隔解碼器，從包含影片相關資料的逗號分隔文字檔案中擷取資料欄位。

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)
