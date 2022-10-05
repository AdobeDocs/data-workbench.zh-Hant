---
description: 配置檔案管理器顯示與工作配置檔案關聯的所有目錄。
title: 建立設定檔管理員
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# 建立設定檔管理員{#create-a-profile-manager}

{{eol}}

配置檔案管理器顯示與工作配置檔案關聯的所有目錄。

您可能想要存取 [!DNL Profile Manager] 而無須導覽其整個目錄結構。 例如， [!DNL Metrics] 和 [!DNL Workspaces] 功能表選項 [!DNL Manage] 「工作區」(Workspace)窗口菜單的菜單允許您分別開啟「配置檔案管理器度量」(Profile Manager Metrics)和「工作區」(Workspaces)資料夾。

如需 [!DNL Profile Manager]，請參閱 [設定檔管理員](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

依預設，您可以存取下列管理員：

* **[!DNL Metrics Manager]:** 顯示「設定檔管理員」的「量度」資料夾的內容。 您可以開啟、編輯、移除或複製每個設定檔中定義的量度。
* **[!DNL Reports Manager]:** 顯示「設定檔管理員」的「報表」資料夾的內容。 您可以開啟、編輯、移除或複製報表工作區，或 [!DNL report.cfg] 檔案。

* **[!DNL Workspaces Manager]:** 顯示「配置檔案管理器」的「工作區」資料夾的內容。 配置 [!DNL Worktop]的頁簽位於此處。 請參閱 [自訂操作台標籤](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench可讓您建立其他設定檔管理員，從 [!DNL Profile Manager]. 您建立的每個管理員都必須 [!DNL .vw] 指定 [!DNL Profile Manager] 目錄，其內容和該窗口的屬性。 您可以使用 [!DNL .vw] 檔案，供任何提供的管理員作為模板。

**建立設定檔管理員的方式**

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Menu]** 目錄來查看其內容。
1. 在功能表目錄內，按一下 **[!UICONTROL Admin]** 目錄，然後 **[!UICONTROL Profile]** 目錄。 此 [!DNL .vw] 現有管理器的檔案位於此處。
1. 在 *設定檔名稱* 欄，按一下右鍵 [!DNL .vw] 檔案(例如， [!DNL Workspaces.vw])，然後按一下 **[!UICONTROL Make Local]**.

   檔案的勾選記號會顯示在 [!DNL User] 欄。

1. 以滑鼠右鍵按一下 [!DNL .vw] 檔案 [!DNL User] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 在 [!DNL Profile Path] 欄位，輸入 [!DNL Profile Manager] 要為其建立新管理器的目錄。 請務必在目錄名稱后面加上斜線(/)。

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

1. 在記事本中，按一下 **[!UICONTROL File]** > **[!UICONTROL Save As]** 將已編輯的檔案儲存至 *Data Workbench安裝資料夾*\用戶\*工作配置檔案名*\Menu\Admin\Profile Management。

   請務必變更 [!DNL .vw] 檔案來反映 [!DNL Profile Manager] 與之對應。

1. （可選）若要讓變更可供工作設定檔的所有使用者使用，請以滑鼠右鍵按一下 [!DNL .vw] 檔案 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>。
