---
description: 「配置檔案管理器」(Profile Manager)顯示與工作配置檔案關聯的所有目錄。
title: 建立設定檔管理員
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# 建立設定檔管理員{#create-a-profile-manager}

「配置檔案管理器」(Profile Manager)顯示與工作配置檔案關聯的所有目錄。

您可能希望訪問[!DNL Profile Manager]的子目錄，而不需要導航其整個目錄結構。 例如，工作區窗口菜單的[!DNL Manage]菜單上提供的[!DNL Metrics]和[!DNL Workspaces]菜單選項可讓您分別開啟「配置檔案管理器」(Profile Manager)「度量」(Metrics)和「工作區」(Workspaces)資料夾。

有關[!DNL Profile Manager]的詳細資訊，請參閱[配置檔案管理器](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)。

依預設，您可以存取下列管理員：

* **[!DNL Metrics Manager]：顯** 示「描述檔管理員」的「度量」檔案夾的內容。您可以開啟、編輯、移除或複製每個描述檔中定義的度量。
* **[!DNL Reports Manager]：顯** 示「描述檔管理員」的「報表」檔案夾的內容。您可以開啟、編輯、移除或複製報表工作區或[!DNL report.cfg]檔案。

* **[!DNL Workspaces Manager]：顯** 示「描述檔管理員」的「工作區」檔案夾的內容。配置[!DNL Worktop]標籤的所有檔案都位於此處。 請參閱[自訂工作台標籤](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)。

Data Workbench允許您建立其他配置式管理器，從[!DNL Profile Manager]中顯示一個子目錄。 您建立的每個管理器都必須有一個[!DNL .vw]檔案，該檔案指定[!DNL Profile Manager]目錄及其顯示內容以及該窗口的屬性。 您可將任何提供的管理員的[!DNL .vw]檔案當做範本。

**要建立配置檔案管理器**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Menu]**&#x200B;目錄以查看其內容。
1. 在菜單目錄中，按一下&#x200B;**[!UICONTROL Admin]**&#x200B;目錄，然後按一下&#x200B;**[!UICONTROL Profile]**&#x200B;目錄。 現有管理器的[!DNL .vw]檔案位於此處。
1. 在&#x200B;*描述檔名稱*&#x200B;欄中，以滑鼠右鍵按一下其中一個[!DNL .vw]檔案的勾號（例如[!DNL Workspaces.vw]），然後按一下&#x200B;**[!UICONTROL Make Local]**。

   檔案的複選標籤會出現在[!DNL User]列中。

1. 按一下右鍵[!DNL User]列中[!DNL .vw]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
1. 在[!DNL Profile Path]欄位中，鍵入要為其建立新管理器的[!DNL Profile Manager]目錄。 請務必在目錄名稱后面加上斜線(/)。

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. 在記事本中，按一下&#x200B;**[!UICONTROL File]** > **[!UICONTROL Save As]**&#x200B;將編輯過的檔案保存到&#x200B;*Data Workbench安裝資料夾*\User\*工作配置檔案名*\Menu\Admin\Profile Management。

   請務必更改[!DNL .vw]檔案的名稱，以反映其對應的[!DNL Profile Manager]目錄。

1. （可選）要使所有工作配置檔案用戶都能使用這些更改，請按一下右鍵[!DNL User]列中[!DNL .vw]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL working profile name]**。
