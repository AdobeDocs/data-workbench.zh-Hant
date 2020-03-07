---
description: 定義擴展尺寸的步驟。
solution: Analytics
title: 定義擴展尺寸
topic: Data workbench
uuid: 25946998-54ca-4595-a2f9-9c593917643a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 定義擴展尺寸{#defining-extended-dimensions}

定義擴展尺寸的步驟。

1. 在資料集設定檔中工作時，請開啟並 [!DNL Profile Manager] 按一下以 **[!UICONTROL Dataset]** 顯示其內容。
1. 開啟 [!DNL Transformation.cfg] 要定義擴 [!DNL Transformation Dataset Include] 展尺寸的檔案或檔案。

   * （建議）若要開啟資料集包含檔案，請參閱資料 [集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

      >[!NOTE]
      >
      >Adobe建議在一或多個新檔案中定義擴充的 [!DNL Transformation Dataset Include] 維度。 如需詳細資訊，請參 [閱建立新資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)。

   * 要開啟文 [!DNL Transformation.cfg] 件，請參 [閱編輯轉換配置檔案](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

1. 按一下右鍵 **[!UICONTROL Transformations]** 並按一下 **[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*。
1. 為延伸維度輸入適當的資訊。 有關轉換類型的說明及其參數的資訊，請參見以下各節：

   * [可計數的維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [簡單尺寸](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [多對多維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [數值維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [非正規維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [時間維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      對於您定義的任何擴展維，可以在「注釋」參數中添加一個或多個注釋行，以進一步描述該維或添加有關其使用的注釋。 若要新增註解，請在標籤上按一 **[!UICONTROL Comments]** 下滑鼠右鍵 **[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**。

1. 在設定檔案中定義擴充維度後，將檔案儲存在本機，並儲存至資料工作台伺服器上的資料集描述檔。
