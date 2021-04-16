---
description: 您可以使用「隱藏」參數或「顯示」參數來隱藏延伸維度，以便它們不會顯示在資料工作台的維度選單中。
title: 隱藏延伸維度
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# 隱藏延伸維度{#hiding-extended-dimensions}

您可以使用「隱藏」參數或「顯示」參數來隱藏延伸維度，以便它們不會顯示在資料工作台的維度選單中。

當您為任一參數輸入適當的設定時，維度名稱不會列在資料工作台的功能表中，但仍會列在描述檔中，可供使用。 任何資料工作台使用者都可將[!DNL Insight.cfg]檔案中的「取消隱藏全部」參數設為true，暫時取消隱藏隱藏的維度。

有關「取消隱藏全部」參數的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中有關資料工作台配置參數的附錄。

以下各節介紹如何使用「隱藏」(Hidden)和「顯示」(Show)參數來隱藏擴展尺寸。

* [使用隱藏參數隱藏擴展Dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [使用Show參數隱藏擴展Dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## 使用隱藏參數{#section-7167a6f6241a4bc78f2f322e048d65cf}隱藏擴展Dimension

「隱藏」參數是可選參數，在[!DNL Transformation Dataset Configuration]檔案中定義擴展尺寸時可使用。

1. 開啟[!DNL Transformation Dataset Configuration]檔案，在其中定義要隱藏的擴展維。 請參閱[編輯現有資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。

1. 在配置窗口中找到所需維的隱藏參數，然後鍵入&#x200B;*true*。
1. 將檔案儲存在本機，然後儲存至伺服器上的適當描述檔。 請參閱[編輯現有資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。

資料集會重新轉換，之後擴充維度不會出現在資料工作台的維度選單中。 有關「隱藏」參數的詳細資訊，請參閱[擴展Dimension](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

如果您變更了「隱藏」參數的設定，則必須重新轉換資料集，才能讓變更生效。

## 使用Show參數{#section-4dceb1079c7f40d2bffc686d1f73f8ad}隱藏擴展Dimension

「顯示」參數不是用於在[!DNL Transformation Dataset Configuration]檔案中定義擴展尺寸的參數之一。 而是在[!DNL .dim]檔案中為您建立的任何衍生維度定義參數。 因此，要使用「顯示」(Show)參數隱藏擴展尺寸，首先必須建立基於擴展尺寸的派生尺寸，如以下過程所述：

1. 使用文本編輯器（如記事本）建立名為&lt;*dimension name*>.dim的空檔案檔案名應與要隱藏的維的名稱相匹配。 例如，要隱藏「下一頁」維，可建立[!DNL Next Page.dim]檔案。

1. 將下列文字新增至檔案：

   * 實體=ref:wdata/model/dim/parent/+name
   * show = bool:false

1. 將檔案保存到配置檔案的Dimension目錄。 您可以視需要將檔案儲存至子目錄。

當您使用「顯示」參數來隱藏延伸維度時，不需要重新轉換資料集，變更就能生效。 您可以選擇隱藏或顯示配置檔案的本地版本中的維（即，可以將[!DNL .dim]檔案保存到您的「用戶」資料夾），也可以將[!DNL .dim]檔案保存到伺服器，以供配置檔案的其他用戶使用。

您也可以使用「顯示」參數來隱藏量度和篩選。 如需詳細資訊，請參閱&#x200B;*Data Workbench使用指南*&#x200B;中的「設定介面和分析功能」一章。
