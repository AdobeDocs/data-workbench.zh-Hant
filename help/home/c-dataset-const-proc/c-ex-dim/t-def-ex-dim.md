---
description: 定義延伸維度的步驟。
title: 定義延伸維度
uuid: 25946998-54ca-4595-a2f9-9c593917643a
exl-id: e1664548-e2b4-47bb-8bec-155c16873e08
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# 定義延伸維度{#defining-extended-dimensions}

定義延伸維度的步驟。

1. 在資料集設定檔中工作時，請開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。
1. 開啟[!DNL Transformation.cfg]檔案或[!DNL Transformation Dataset Include]檔案，您要在其中定義擴展維。

   * （建議）若要開啟資料集包含檔案，請參閱[資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

      >[!NOTE]
      >
      >Adobe建議在一個或多個新[!DNL Transformation Dataset Include]檔案中定義擴展維。 如需詳細資訊，請參閱[建立新資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e)。

   * 要開啟[!DNL Transformation.cfg]檔案，請參閱[編輯轉換配置檔案](../../../home/c-dataset-const-proc/c-trans-config-file/t-edit-trans-config-file.md#task-cfef4142c1bf4437a669d1fdc75cabbc)。

1. 按一下右鍵&#x200B;**[!UICONTROL Transformations]**，然後按一下&#x200B;**[!UICONTROL Add new]** > *&lt;**[!UICONTROL Extended dimension type]**>*。
1. 輸入延伸維度的適當資訊。 有關轉換類型的說明及其參數的資訊，請參閱以下各節：

   * [可數維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)
   * [簡單維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-simple-dim.md#concept-c1d804dac4094489afe61560d2908181)
   * [多對多維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-many-dim.md#concept-5ed3cca8b2194d4f96134f6238040998)
   * [數值維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-num-dim.md#concept-8513b9afaff447c8b334410b565b91ed)
   * [非正規維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-denormal-dim.md#concept-54a2600b8ee748b7acff405daccf3489)
   * [時間維度](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-time-dim.md#concept-1e4eeb8d33964bb2a8d5768d6439df67)

      對於您定義的任何擴展維，可以在「注釋」參數中添加一個或多個注釋行，以進一步說明該維或添加有關其使用的注釋。 若要新增註解，請以滑鼠右鍵按一下&#x200B;**[!UICONTROL Comments]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Comment Line]**。

1. 在設定檔案中定義延伸維度後，請將檔案儲存在本機，然後儲存至Data Workbench伺服器上的資料集設定檔。
