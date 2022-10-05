---
description: 伺服器檔案管理器顯示Data Workbench伺服器安裝目錄中的所有目錄，包括配置和查找檔案。
title: 建立伺服器檔案管理員
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# 建立伺服器檔案管理員{#create-a-server-files-manager}

{{eol}}

伺服器檔案管理器顯示Data Workbench伺服器安裝目錄中的所有目錄，包括配置和查找檔案。

您可能想要存取 [!DNL Server Files Manager] 而無須導覽其整個目錄結構，或只顯示幾個子目錄以滿足特定需求。 例如，您可能想要建立個別 [!DNL Server Files Manager] 僅顯示「存取控制」和「使用者」子目錄，讓您管理使用者及其存取權。

您建立的每個管理員都必須 [!DNL .vw] 檔案。 您可以使用 [!DNL Server Files.vw] 檔案作為範本。

如需 [!DNL Server Files Manager]，請參閱 [伺服器檔案管理器](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**建立伺服器檔案管理器**

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Menu]** 目錄，然後 **[!UICONTROL Admin]** 目錄。 此 [!DNL Server Files.vw] 檔案的位置。
1. 在 *設定檔名稱* 欄，按一下右鍵 [!DNL Server Files.vw] 按一下 **[!UICONTROL Make Local]**. 檔案的勾選記號會顯示在 [!DNL User] 欄。
1. 以滑鼠右鍵按一下 [!DNL Server Files.vw] 檔案 [!DNL User] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 此 [!DNL Server Files.vw] 檔案開啟。
1. 若要移除目錄，請以滑鼠右鍵按一下 [!DNL Server Files Manager] 按一下 **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. 若要新增目錄，請以滑鼠右鍵按一下 [!DNL Server Files Manager]，按一下 **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   在URI欄位中鍵入目錄的URI，然後按一下 **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >您可以在URI欄位中指定多個目錄。 例如，如果您輸入 [!DNL Profiles\Marketing\]，則伺服器檔案管理員包含行銷子目錄，但設定檔目錄中沒有其他子目錄。

1. 以滑鼠右鍵按一下 [!DNL Server Files Manager] 按一下 **[!UICONTROL Save]**.
1. 若要建立新管理器，請在 [!DNL File Name] 欄位，然後按一下 **[!UICONTROL Save]**. 要覆蓋現有管理器，請按一下 **[!UICONTROL Save]**.
1. （可選）若要讓變更可供工作設定檔的所有使用者使用，請以滑鼠右鍵按一下 [!DNL .vw] 檔案 [!DNL User] 欄。

   然後，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
