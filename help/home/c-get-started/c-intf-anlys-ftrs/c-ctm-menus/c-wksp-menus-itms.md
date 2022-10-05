---
description: 這些步驟僅適用於為「工作區窗口」(Workspace Window)菜單建立子菜單和菜單項。
title: 建立工作區功能表和功能表項目
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# 建立工作區功能表和功能表項目{#create-a-workspace-menu-and-menu-item}

{{eol}}

這些步驟僅適用於為「工作區窗口」(Workspace Window)菜單建立子菜單和菜單項。

您可以透過建立新資料夾和新的衍生量度和維度來自訂量度和維度功能表。 如需詳細資訊，請參閱 [建立和編輯衍生量度](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) 和 [建立和編輯衍生Dimension](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**建立新工作區窗口菜單**

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Menu]** 目錄來查看其內容。
1. 在 [!DNL User] 列，按一下 **[!UICONTROL Create]** > **[!UICONTROL Folder]**. 名為「新建資料夾」的資料夾出現在 [!DNL File] 欄 [!DNL Menu].

   >[!NOTE]
   >
   >您也可以為功能表目錄中的任何子目錄建立新資料夾。

1. 在 [!DNL User] 欄，並在「目錄」參數中鍵入新名稱。
1. 將需要的檔案新增至新資料夾。
1. （選用）在 [!DNL User] 欄，按一下 **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   安 [!DNL order.txt] 檔案會顯示在 [!DNL File] 欄中，新檔案的複選標籤將出現在 [!DNL User] 欄。

1. （選用）編輯 [!DNL order.txt] 檔案。 請參閱 [使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. （可選）若要讓變更可供工作設定檔的所有使用者使用，請在資料夾的白勾號上按一下滑鼠右鍵 [!DNL User] 欄，按一下 **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**將新菜單項添加到現有菜單**

1. 完成下列其中一個步驟：

   * 建立新項目（視覺效果、附註等）以新增至功能表：

      1. 在Data Workbench中開啟工作區並建立所需項目。
      1. 將項目保存到以下目錄：

         *Data Workbench安裝目錄*\用戶\*工作配置檔案名*\工作

      1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Work]** 目錄來查看其內容。
      1. 在 [!DNL User] 欄，按一下右鍵所需檔案的複選標籤，然後按一下 **[!UICONTROL Copy]**.
      1. 在 [!DNL User] 欄，按一下 **[!UICONTROL Paste]**.

         檔案的副本會顯示在 [!DNL File] 欄中，新檔案的複選標籤將出現在 [!DNL User] 欄。
   * 將現有項目從一個功能表（資料夾）複製並貼到另一個功能表（資料夾）:

      1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Menu]** 目錄來查看其內容。
      1. 在 *工作設定檔名稱* 欄，按一下右鍵所需檔案的複選標籤，然後按一下 **[!UICONTROL Make Local]**.
      1. 以滑鼠右鍵按一下 [!DNL User] 欄，按一下 **[!UICONTROL Copy]**.
      1. 在 [!DNL User] 欄，按一下 **[!UICONTROL Paste]**. 檔案的副本會顯示在 [!DNL File] 欄中，新檔案的複選標籤將出現在 [!DNL User] 欄。


1. （選用）編輯 [!DNL order.txt] 檔案。 請參閱 [使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. （選用）若要讓變更可供工作設定檔的所有使用者使用，請在中以滑鼠右鍵按一下每個檔案的白勾號 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. （可選）為避免多個菜單中出現菜單項，應按一下右鍵檔案的複選標籤，從其原始資料夾中刪除相應的檔案 *工作設定檔名稱* 欄，按一下 **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   在 [!DNL User] 欄。
