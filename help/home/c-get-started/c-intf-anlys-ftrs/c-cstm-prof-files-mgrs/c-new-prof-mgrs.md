---
description: 配置檔案管理器顯示與工作配置檔案關聯的所有目錄。
title: 建立設定檔管理員
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# 建立設定檔管理員{#create-a-profile-manager}

配置檔案管理器顯示與工作配置檔案關聯的所有目錄。

您可能希望訪問[!DNL Profile Manager]的子目錄，而不需要瀏覽其整個目錄結構。 例如，工作區窗口菜單的[!DNL Manage]菜單上可用的[!DNL Metrics]和[!DNL Workspaces]菜單選項允許您分別開啟「配置檔案管理器」(Profile Manager)「度量」(Metrics)和「工作區」(Workspaces)資料夾。

有關[!DNL Profile Manager]的詳細資訊，請參閱[設定檔管理員](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)。

依預設，您可以存取下列管理員：

* **[!DNL Metrics Manager]:** 顯示「設定檔管理員」的「量度」資料夾的內容。您可以開啟、編輯、移除或複製每個設定檔中定義的量度。
* **[!DNL Reports Manager]:** 顯示「設定檔管理員」的「報表」資料夾的內容。您可以開啟、編輯、移除或複製報表工作區或[!DNL report.cfg]檔案。

* **[!DNL Workspaces Manager]:** 顯示「配置檔案管理器」的「工作區」資料夾的內容。配置[!DNL Worktop]頁簽的所有檔案都位於此處。 請參閱[自訂操作台標籤](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)。

Data Workbench可讓您建立其他設定檔管理員，從[!DNL Profile Manager]顯示一個子目錄。 您建立的每個管理員都必須有一個[!DNL .vw]檔案，該檔案指定[!DNL Profile Manager]目錄的內容以及該窗口的屬性。 您可以將提供的任何管理器的[!DNL .vw]檔案用作模板。

**建立設定檔管理員的方式**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Menu]**&#x200B;目錄以查看其內容。
1. 在菜單目錄中，按一下&#x200B;**[!UICONTROL Admin]**&#x200B;目錄，然後按一下&#x200B;**[!UICONTROL Profile]**&#x200B;目錄。 現有管理器的[!DNL .vw]檔案位於此處。
1. 在&#x200B;*設定檔名稱*&#x200B;欄中，以滑鼠右鍵按一下其中一個[!DNL .vw]檔案的勾號（例如[!DNL Workspaces.vw]），然後按一下&#x200B;**[!UICONTROL Make Local]**。

   [!DNL User]列中將顯示檔案的複選標籤。

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

1. 在記事本中，按一下&#x200B;**[!UICONTROL File]** > **[!UICONTROL Save As]**&#x200B;將編輯的檔案保存到&#x200B;*Data Workbench安裝資料夾*\User\*工作配置檔案名*\Menu\Admin\Profile Management。

   請務必更改[!DNL .vw]檔案的名稱，以反映與之對應的[!DNL Profile Manager]中的目錄。

1. （可選）要使更改可供工作配置檔案的所有用戶使用，請在[!DNL User]列中按一下右鍵[!DNL .vw]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**。
