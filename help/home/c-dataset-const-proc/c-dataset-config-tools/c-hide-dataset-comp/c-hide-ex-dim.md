---
description: 您可以使用「隱藏」參數或「顯示」參數來隱藏延伸維度，使其不會顯示在Data Workbench的「維度」功能表中。
title: 隱藏延伸維度
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
exl-id: 5baccf39-6f3b-40a1-b1c0-a8e5d6a61211
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 1%

---

# 隱藏延伸維度{#hiding-extended-dimensions}

您可以使用「隱藏」參數或「顯示」參數來隱藏延伸維度，使其不會顯示在Data Workbench的「維度」功能表中。

當您為任一參數輸入適當的設定時，Data Workbench的功能表中不會列出維度名稱，但維度名稱仍在設定檔中，且可供使用。 任何Data Workbench使用者都可將[!DNL Insight.cfg]檔案中的「全部取消隱藏」參數設為true，以暫時取消隱藏維度。

如需「全部取消隱藏」參數的詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中Data Workbench設定參數的附錄。

以下幾節說明如何使用「隱藏」(Hidden)和「顯示」(Show)參數來隱藏擴展尺寸。

* [使用隱藏參數隱藏擴展Dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [使用Show參數隱藏擴展Dimension](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## 使用隱藏參數{#section-7167a6f6241a4bc78f2f322e048d65cf}隱藏擴展Dimension

「隱藏」參數是可選參數，在[!DNL Transformation Dataset Configuration]檔案中定義擴展維時可使用。

1. 開啟[!DNL Transformation Dataset Configuration]檔案，其中定義了要隱藏的擴展維。 請參閱[編輯現有的資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。

1. 在設定視窗中找出所需維度的隱藏參數，並輸入&#x200B;*true*。
1. 將檔案儲存在本機，然後儲存至伺服器上的適當設定檔。 請參閱[編輯現有的資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。

資料集重新轉換，之後擴充的維度不會出現在Data Workbench的維度功能表中。 有關「隱藏」參數的詳細資訊，請參閱[擴展Dimension](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

如果您變更了「隱藏」參數的設定，則必須重新轉換資料集，變更才會生效。

## 使用Show參數{#section-4dceb1079c7f40d2bffc686d1f73f8ad}隱藏擴展Dimension

Show參數不是可用於定義[!DNL Transformation Dataset Configuration]檔案中擴展維的參數之一。 而是在[!DNL .dim]檔案中為您建立的任何衍生維度定義參數。 因此，要使用Show參數來隱藏擴展維，首先必須建立基於擴展維的派生維，如以下過程中所述：

1. 使用Notepad等文本編輯器建立名為&lt;*dimension name*>.dim的空檔案。檔案名應與要隱藏的維的名稱相匹配。 例如，若要隱藏「下一頁」維度，需建立[!DNL Next Page.dim]檔案。

1. 將下列文字新增至檔案：

   * entity = ref:wdata/model/dim/parent/+name
   * show = bool:false

1. 將檔案儲存至設定檔的Dimension目錄。 您可以視需要將檔案儲存至子目錄。

使用「顯示」參數來隱藏延伸維度時，您不必重新轉換資料集即可讓變更生效。 您可以選擇隱藏或顯示配置檔案的本地版本中的維（即，可以將[!DNL .dim]檔案保存到用戶資料夾），或將[!DNL .dim]檔案保存到伺服器，供配置檔案的其他用戶使用。

您也可以使用「顯示」參數來隱藏量度和篩選器。 如需詳細資訊，請參閱&#x200B;*Data Workbench使用手冊*&#x200B;中的設定介面和分析功能一章。
