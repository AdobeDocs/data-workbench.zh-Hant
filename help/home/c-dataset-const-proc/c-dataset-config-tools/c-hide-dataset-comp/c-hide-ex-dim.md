---
description: 您可以使用「隱藏」參數或「顯示」參數來隱藏延伸維度，以便它們不會顯示在資料工作台的維度選單中。
solution: Analytics
title: 隱藏延伸維度
topic: Data workbench
uuid: c32f47ad-0246-4611-b54c-0c9f0eb396bd
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 隱藏延伸維度{#hiding-extended-dimensions}

您可以使用「隱藏」參數或「顯示」參數來隱藏延伸維度，以便它們不會顯示在資料工作台的維度選單中。

當您為任一參數輸入適當的設定時，維度名稱不會列在資料工作台的功能表中，但仍會列在描述檔中，可供使用。 任何資料工作台使用者都可將檔案中的「取消隱藏全部」參數設定為true，暫時取消隱藏 [!DNL Insight.cfg] 的維度。

如需「取消隱藏全部」參數的詳細資訊，請參閱「資料工作台使用指南」中資料工作台 *組態參數的附錄*。

以下各節介紹如何使用「隱藏」(Hidden)和「顯示」(Show)參數來隱藏擴展尺寸。

* [使用隱藏參數隱藏擴展尺寸](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-7167a6f6241a4bc78f2f322e048d65cf)
* [使用顯示參數隱藏擴展尺寸](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-ex-dim.md#section-4dceb1079c7f40d2bffc686d1f73f8ad)

## 使用隱藏參數隱藏擴展尺寸 {#section-7167a6f6241a4bc78f2f322e048d65cf}

「隱藏」參數是可選參數，可在檔案中定義擴展尺寸時使 [!DNL Transformation Dataset Configuration] 用。

1. 打 [!DNL Transformation Dataset Configuration] 開要隱藏的擴展維定義在其中的檔案。 請參閱 [編輯現有資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。

1. 在配置窗口中找到所需維的隱藏參數，然後鍵入 *true*。
1. 將檔案儲存在本機，然後儲存至伺服器上的適當描述檔。 請參閱 [編輯現有資料集包含檔案](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077)。

資料集會重新轉換，之後擴充維度不會出現在資料工作台的維度選單中。 如需「隱藏」參數的詳細資訊，請參閱「延伸 [尺寸」](../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

如果您變更了「隱藏」參數的設定，則必須重新轉換資料集，才能讓變更生效。

## 使用顯示參數隱藏擴展尺寸 {#section-4dceb1079c7f40d2bffc686d1f73f8ad}

「顯示」參數不是可用於定義檔案中擴展尺寸的參數 [!DNL Transformation Dataset Configuration] 之一。 而是在檔案中為您建立的 [!DNL .dim] 任何派生尺寸定義參數。 因此，要使用「顯示」(Show)參數隱藏擴展尺寸，首先必須建立基於擴展尺寸的派生尺寸，如以下過程所述：

1. 使用文本編輯器（如記事本）建立一個名為&lt;*dimension name*>.dim的空檔案檔案名應與要隱藏的維的名稱相匹配。 例如，若要隱藏「下一頁」維度，您應建立檔 [!DNL Next Page.dim] 案。

1. 將下列文字新增至檔案：

   * 實體=ref:wdata/model/dim/parent/+name
   * show = bool:false

1. 將檔案保存到配置檔案的「維」目錄。 您可以視需要將檔案儲存至子目錄。

當您使用「顯示」參數來隱藏延伸維度時，不需要重新轉換資料集，變更就能生效。 您可以選擇隱藏或顯示配置檔案的本地版本中的維（即，可以將檔案保存到「用戶」資料夾），或者將檔案保存到伺服器，以供 [!DNL .dim][!DNL .dim] 該配置檔案的其他用戶使用。

您也可以使用「顯示」參數來隱藏量度和篩選。 如需詳細資訊，請參閱資料工作台使用指南中的「設定介面 *和分析功能」一章*。
