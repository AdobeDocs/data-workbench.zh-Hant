---
description: 「伺服器檔案管理員」會顯示「資料工作台」伺服器安裝目錄中的所有目錄，包括設定和查閱檔案。
solution: Analytics
title: 建立伺服器檔案管理器
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 建立伺服器檔案管理器{#create-a-server-files-manager}

「伺服器檔案管理員」會顯示「資料工作台」伺服器安裝目錄中的所有目錄，包括設定和查閱檔案。

您可能需要訪問該部分，而 [!DNL Server Files Manager] 不需要導航其整個目錄結構，或只顯示幾個子目錄以滿足特定需要。 例如，您可能想要建立個別，只顯 [!DNL Server Files Manager] 示「存取控制」和「使用者」子目錄，讓您管理使用者及其存取權。

您建立的每個管理員都必須有 [!DNL .vw] 檔案。 您可以將檔 [!DNL Server Files.vw] 案當做範本使用。

有關的詳細資訊 [!DNL Server Files Manager]，請參 [閱伺服器檔案管理器](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)。

**建立伺服器檔案管理器**

1. 在中， [!DNL Profile Manager]按一下目 **[!UICONTROL Menu]** 錄，然後按一下目 **[!UICONTROL Admin]** 錄。 文 [!DNL Server Files.vw] 件位於此處。
1. 在描述 *檔名稱欄* ，以滑鼠右鍵按一下檔案的核取 [!DNL Server Files.vw] 標籤，然後按一下 **[!UICONTROL Make Local]**。 該檔案的複選標籤將出現在該 [!DNL User] 列中。
1. 按一下右鍵列中檔案的復 [!DNL Server Files.vw] 選標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 檔案 [!DNL Server Files.vw] 隨即開啟。
1. 要刪除目錄，請按一下右鍵目錄的頂部邊框， [!DNL Server Files Manager] 然後按一下 **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*。
1. 若要新增目錄，請以滑鼠右鍵按一下目錄的上 [!DNL Server Files Manager]邊框， **[!UICONTROL Server Directories]** 按一 **[!UICONTROL Add]** 下> **[!UICONTROL Directory]**。

   在URI欄位中輸入目錄的URI，然後按一下 **[!UICONTROL OK]**。

   >[!NOTE]
   >
   >可以在URI欄位中指定多個目錄。 例如，如果鍵入[!DNL Profiles\Marketing\]，則伺服器檔案管理器包含Marketing子目錄，但Profiles目錄中沒有其他子目錄。

1. 按一下右鍵頂部邊框的頂部，然 [!DNL Server Files Manager] 後按一下 **[!UICONTROL Save]**。
1. 要建立新管理器，請更改欄位中的檔案名， [!DNL File Name] 然後按一下 **[!UICONTROL Save]**。 若要覆寫現有的管理員，請按一下 **[!UICONTROL Save]**。
1. （可選）要使更改可供工作配置檔案的所有用戶使用，請按一下右鍵列中文 [!DNL .vw] 件的複選 [!DNL User] 標籤。

   然後，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

