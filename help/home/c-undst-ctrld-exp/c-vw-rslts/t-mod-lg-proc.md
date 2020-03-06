---
description: 您必須將x-experity欄位新增至Log Processing.cfg檔案，此檔案可用來建立擴充的維度。
solution: Insight,Analytics
title: 修改Log Processing.cfg
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改Log Processing.cfg{#modifying-log-processing-cfg}

您必須將x-experity欄位新增至Log Processing.cfg檔案，此檔案可用來建立擴充的維度。

請參 [閱修改Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6)。

**要修改Log Processing.cfg**

1. 在中， [!DNL Insight]在工作區中 [!DNL Profile Manager] 按一下滑鼠右鍵並按一下 **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**，或在標籤上開啟「描述檔管理」工作區，以開啟 [!DNL Admin] 該工作區。
1. 在中，單 [!DNL Profile Manager]擊以 **[!UICONTROL Dataset]** 顯示其內容。
1. 按一下右鍵旁邊的複選標 [!DNL Log Processing.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。 出現 [!DNL Log Processing.cfg] 窗口。
1. 按一 **[!UICONTROL Fields]** 下以顯示其內容。
1. 在目前清單中，以滑鼠右鍵按一下最後一個欄位，然後按一 **[!UICONTROL Add new]** 下> **[!UICONTROL Field]**。
1. 在新建立的欄位中鍵入x-experice，如下列範例所示：

   ![步驟資訊](assets/logprocessing.png)

1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。
1. 在中， [!DNL Profile Manager]按一下右鍵列中的複選標 [!DNL Log Processing.cfg] 記，然 [!DNL User] 後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]*** >將本地對工作配置檔案進行的更改保存。

   >[!NOTE]
   >
   >資料集會立即開始重新處理。

   如需記錄處理和欄位的詳細資訊，請參閱資料集 *設定指南*。

