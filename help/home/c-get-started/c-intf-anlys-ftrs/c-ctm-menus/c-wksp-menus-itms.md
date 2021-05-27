---
description: 這些步驟僅適用於為「工作區窗口」(Workspace Window)菜單建立子菜單和菜單項。
title: 建立工作區功能表和功能表項目
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# 建立工作區功能表和功能表項目{#create-a-workspace-menu-and-menu-item}

這些步驟僅適用於為「工作區窗口」(Workspace Window)菜單建立子菜單和菜單項。

您可以透過建立新資料夾和新的衍生量度和維度來自訂量度和維度功能表。 如需詳細資訊，請參閱[建立和編輯衍生量度](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40)和[建立和編輯衍生Dimension](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)。

**建立新工作區窗口菜單**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Menu]**&#x200B;目錄以查看其內容。
1. 在菜單目錄的[!DNL User]列中，按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL Folder]**。 名為「新建資料夾」的資料夾出現在[!DNL Menu]的[!DNL File]列中。

   >[!NOTE]
   >
   >您也可以為功能表目錄中的任何子目錄建立新資料夾。

1. 按一下右鍵該資料夾的[!DNL User]列，並在Dir參數中鍵入新名稱，以更名新資料夾。
1. 將需要的檔案新增至新資料夾。
1. （可選）在新資料夾的[!DNL User]欄中，按一下&#x200B;**[!UICONTROL Create]** > **[!UICONTROL order.txt]**。

   新資料夾的[!DNL File]列中顯示一個[!DNL order.txt]檔案，而新檔案的複選標籤在[!DNL User]列中顯示。

1. （可選）視需要編輯[!DNL order.txt]檔案。 請參閱[使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。
1. （可選）要使工作配置檔案的所有用戶都能使用更改，請按一下右鍵[!DNL User]列中資料夾的白勾號，然後按一下&#x200B;**[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*。

**將新菜單項添加到現有菜單**

1. 完成下列其中一個步驟：

   * 建立新項目（視覺效果、附註等）以新增至功能表：

      1. 在Data Workbench中開啟工作區，並建立所需項目。
      1. 將項目保存到以下目錄：

         *Data Workbench安裝目錄*\User\*工作設定檔名稱*\Work

      1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Work]**&#x200B;目錄以查看其內容。
      1. 在[!DNL User]欄中，以滑鼠右鍵按一下所需檔案的勾號，然後按一下&#x200B;**[!UICONTROL Copy]**。
      1. 在所需資料夾的[!DNL User]欄中，按一下&#x200B;**[!UICONTROL Paste]**。

         新資料夾的[!DNL File]列中會顯示檔案副本，而[!DNL User]列中會顯示新檔案的複選標籤。
   * 將現有項目從一個功能表（資料夾）複製並貼到另一個功能表（資料夾）:

      1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Menu]**&#x200B;目錄以查看其內容。
      1. 在&#x200B;*工作設定檔名稱*&#x200B;欄中，以滑鼠右鍵按一下所需檔案的勾號，然後按一下&#x200B;**[!UICONTROL Make Local]**。
      1. 按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Copy]**。
      1. 在所需資料夾的[!DNL User]欄中，按一下&#x200B;**[!UICONTROL Paste]**。 新資料夾的[!DNL File]列中會顯示檔案副本，而[!DNL User]列中會顯示新檔案的複選標籤。


1. （可選）視需要編輯[!DNL order.txt]檔案。 請參閱[使用Order.txt檔案自訂功能表](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)。
1. （可選）要使工作配置檔案的所有用戶都能使用更改，請按一下右鍵[!DNL User]列中每個檔案的白勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。
1. （可選）為避免多個菜單中出現菜單項，應按一下右鍵&#x200B;*工作配置檔案名*&#x200B;列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Remove]** > **[!UICONTROL Yes]**，從其原始資料夾中刪除相應的檔案。

   在[!DNL User]欄中對檔案的複選標籤重複此步驟。
