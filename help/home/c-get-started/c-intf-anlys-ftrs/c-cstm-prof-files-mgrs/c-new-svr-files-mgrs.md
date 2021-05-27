---
description: 伺服器檔案管理器顯示Data Workbench伺服器安裝目錄中的所有目錄，包括配置和查找檔案。
title: 建立伺服器檔案管理員
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# 建立伺服器檔案管理員{#create-a-server-files-manager}

伺服器檔案管理器顯示Data Workbench伺服器安裝目錄中的所有目錄，包括配置和查找檔案。

您可能不需要瀏覽[!DNL Server Files Manager]的整個目錄結構或僅顯示幾個子目錄來滿足特定需求，就想訪問的一部分。 例如，您可能想要建立單獨的[!DNL Server Files Manager]，僅顯示「存取控制」和「使用者」子目錄，以便您管理使用者及其存取權。

您建立的每個管理員都必須有[!DNL .vw]檔案。 可以將[!DNL Server Files.vw]檔案用作模板。

有關[!DNL Server Files Manager]的詳細資訊，請參閱[伺服器檔案管理器](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)。

**建立伺服器檔案管理器**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Menu]**&#x200B;目錄，然後按一下&#x200B;**[!UICONTROL Admin]**&#x200B;目錄。 [!DNL Server Files.vw]檔案位於此處。
1. 在&#x200B;*設定檔名稱*&#x200B;欄中，以滑鼠右鍵按一下[!DNL Server Files.vw]檔案的勾號，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示檔案的複選標籤。
1. 按一下右鍵[!DNL User]列中[!DNL Server Files.vw]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 將開啟[!DNL Server Files.vw]檔案。
1. 要刪除目錄，請按一下右鍵[!DNL Server Files Manager]的上邊框，然後按一下&#x200B;**[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*。
1. 要添加目錄，請按一下右鍵[!DNL Server Files Manager]的上邊框，按一下&#x200B;**[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**。

   在URI欄位中鍵入目錄的URI，然後按一下&#x200B;**[!UICONTROL OK]**。

   >[!NOTE]
   >
   >您可以在URI欄位中指定多個目錄。 例如，如果您輸入 [!DNL Profiles\Marketing\]，則伺服器檔案管理員會包含Marketing子目錄，但Profiles目錄中沒有其他子目錄。

1. 按一下右鍵[!DNL Server Files Manager]頂部邊框，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 要建立新管理器，請更改[!DNL File Name]欄位中的檔案名，然後按一下&#x200B;**[!UICONTROL Save]**。 要覆蓋現有管理器，請按一下&#x200B;**[!UICONTROL Save]**。
1. （可選）要使更改可供工作配置檔案的所有用戶使用，請在[!DNL User]列中按一下右鍵[!DNL .vw]檔案的複選標籤。

   然後，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
