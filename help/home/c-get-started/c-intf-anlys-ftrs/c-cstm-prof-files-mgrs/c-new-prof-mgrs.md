---
description: 「配置檔案管理器」(Profile Manager)顯示與工作配置檔案關聯的所有目錄。
solution: Analytics
title: 建立描述檔管理員
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 建立描述檔管理員{#create-a-profile-manager}

「配置檔案管理器」(Profile Manager)顯示與工作配置檔案關聯的所有目錄。

您可能希望訪問的子目錄，而 [!DNL Profile Manager] 不需要導航其整個目錄結構。 例如，工作區 [!DNL Metrics] 窗口菜單 [!DNL Workspaces] 中的可用菜單和菜單 [!DNL Manage] 選項可讓您分別開啟「配置檔案管理器度量」和「工作區」資料夾。

有關的詳細資訊 [!DNL Profile Manager]，請參 [閱The Profile Manager](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)。

依預設，您可以存取下列管理員：

* **[!DNL Metrics Manager]:**顯示「描述檔管理員」的「度量」檔案夾的內容。 您可以開啟、編輯、移除或複製每個描述檔中定義的度量。
* **[!DNL Reports Manager]:**顯示「描述檔管理員」的「報表」檔案夾的內容。 您可以開啟、編輯、移除或複製報表工作區或[!DNL report.cfg]檔案。

* **[!DNL Workspaces Manager]:**顯示「描述檔管理員」的「工作區」檔案夾的內容。 所有用於設定標籤[!DNL Worktop]的檔案都位於這裡。 請參閱[自訂工作台標籤](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)。

資料工作台可讓您建立其他描述檔管理員，從中顯示一個子目錄 [!DNL Profile Manager]。 您建立的每個管理器都必須有 [!DNL .vw] 一個檔案，該檔案指 [!DNL Profile Manager] 定其顯示內容的目錄以及該窗口的屬性。 您可以將任何 [!DNL .vw] 提供的管理員的檔案當做範本使用。

**要建立配置檔案管理器**

1. 在中，單 [!DNL Profile Manager]擊該目 **[!UICONTROL Menu]** 錄可查看其內容。
1. 在「菜單」目錄中，按一下 **[!UICONTROL Admin]** 目錄，然後按一下目 **[!UICONTROL Profile]** 錄。 現有 [!DNL .vw] 管理員的檔案位於此處。
1. 在描 *述檔名* 欄中，以滑鼠右鍵按一下其中一個檔案的 [!DNL .vw] 核取標籤(例如 [!DNL Workspaces.vw])，然後按一下 **[!UICONTROL Make Local]**。

   該檔案的複選標籤將出現在該 [!DNL User] 列中。

1. 按一下右鍵列中檔案的復 [!DNL .vw] 選標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
1. 在字 [!DNL Profile Path] 段中，鍵入 [!DNL Profile Manager] 要為其建立新管理器的目錄。 請務必在目錄名稱后面加上斜線(/)。

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

1. 在記事本中，按一 **[!UICONTROL File]** 下> **[!UICONTROL Save As]** 將編輯好的檔案儲存至「資料工作台」安裝資料夾 **\User\*工作設定檔名稱*\Menu\Admin\Profile Management。

   請務必更改檔案的名 [!DNL .vw] 稱，以反映其對應的 [!DNL Profile Manager] 目錄。

1. （可選）要使所有使用者都能使用工作設定檔的變更，請在欄中以滑鼠右鍵按一下 [!DNL .vw] 該檔案的 [!DNL User] 核取標籤，然後按 **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>。

