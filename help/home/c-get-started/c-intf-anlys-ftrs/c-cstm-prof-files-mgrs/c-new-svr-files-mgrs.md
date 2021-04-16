---
description: 「伺服器檔案管理器」顯示Data Workbench伺服器安裝目錄中的所有目錄，包括配置和查找檔案。
title: 建立伺服器檔案管理員
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# 建立伺服器檔案管理員{#create-a-server-files-manager}

「伺服器檔案管理器」顯示Data Workbench伺服器安裝目錄中的所有目錄，包括配置和查找檔案。

您可能希望訪問[!DNL Server Files Manager]的一部分，而無需瀏覽其整個目錄結構或只顯示幾個子目錄以滿足特定需求。 例如，您可能想要建立個別的[!DNL Server Files Manager]，僅顯示「訪問控制」和「用戶」子目錄，以便管理用戶及其訪問。

您建立的每個管理器都必須有一個[!DNL .vw]檔案。 您可以將[!DNL Server Files.vw]檔案當做範本使用。

有關[!DNL Server Files Manager]的詳細資訊，請參閱[伺服器檔案管理器](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)。

**建立伺服器檔案管理器**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Menu]**&#x200B;目錄，然後按一下&#x200B;**[!UICONTROL Admin]**&#x200B;目錄。 [!DNL Server Files.vw]檔案位於此處。
1. 在&#x200B;*描述檔名稱*&#x200B;欄中，以滑鼠右鍵按一下[!DNL Server Files.vw]檔案的核取標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 檔案的複選標籤會出現在[!DNL User]列中。
1. 按一下右鍵[!DNL User]列中[!DNL Server Files.vw]檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 將開啟[!DNL Server Files.vw]檔案。
1. 要刪除目錄，請按一下右鍵[!DNL Server Files Manager]的頂部邊框，然後按一下&#x200B;**[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > ***[!UICONTROL directory name]**>*。
1. 要添加目錄，請按一下右鍵[!DNL Server Files Manager]的頂部邊框，按一下&#x200B;**[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**。

   在URI欄位中輸入目錄的URI，然後按一下&#x200B;**[!UICONTROL OK]**。

   >[!NOTE]
   >
   >可以在URI欄位中指定多個目錄。 例如，如果您鍵入 [!DNL Profiles\Marketing\]，則伺服器檔案管理器包含Marketing子目錄，但Profiles目錄中沒有其他子目錄。

1. 按一下右鍵[!DNL Server Files Manager]頂部邊框的頂部，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 要建立新管理器，請更改[!DNL File Name]欄位中的檔案名，然後按一下&#x200B;**[!UICONTROL Save]**。 要覆蓋現有的管理器，請按一下&#x200B;**[!UICONTROL Save]**。
1. （可選）要使所有工作配置檔案用戶都能使用這些更改，請按一下右鍵[!DNL User]列中[!DNL .vw]檔案的複選標籤。

   然後，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
