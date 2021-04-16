---
description: 您可以使用「描述檔管理員」來下載您要修改的檔案。
title: 修改使用者設定檔中的本機檔案
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# 修改使用者設定檔中的本機檔案{#modify-local-files-in-the-user-profile}

您可以使用「描述檔管理員」來下載您要修改的檔案。

您可能想要下載檔案以原始檔案版本覆寫現有的本機檔案，或開啟、檢視和修改無法從工作區功能表存取的檔案。

**下載檔案**

1. 在[!DNL Profile Manager]中，開啟必要的檔案夾和子檔案夾，以找出您要下載的檔案。
1. 按一下右鍵檔案名稱旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。

   >[!NOTE]
   >
   >配置([!DNL .cfg])、維([!DNL .dim])和度量([!DNL .metric])檔案可以直接在配置檔案資料夾中編輯並保存到伺服器中，而無需將它們設定為本地檔案並單獨保存到伺服器中。 只需按一下右鍵檔案名稱旁的複選標籤，然後按一下工作站&#x200B;**中的&#x200B;**[!UICONTROL Open]**>**。

將檔案下載到本地電腦後，[!DNL User]列中會出現複選標籤，表示該檔案的本地副本駐留在電腦的User\*profile name*資料夾中。 請注意，複選標籤與&#x200B;*描述檔名稱*&#x200B;欄中的複選標籤顏色相同。 這表示本地檔案與&#x200B;*配置檔案名*&#x200B;資料夾中的檔案具有相同的修改日期和時間。

**要修改檔案**

1. 按一下右鍵[!DNL User]列中檔案名旁的複選標籤。
1. 根據您要編輯檔案的方式，按一下下列其中一個功能表選項：

   * **[!UICONTROL Open]** >  **[!UICONTROL in workstation]** if you are editing a file [!DNL .vw]  or  [!DNL .cfg] file in a workspace.

   * **開啟** > **in vw。編輯器**如果您正在編輯。vw檔案以添加新參數。

   * **[!UICONTROL Open]** >  **[!UICONTROL In Notepad]** if you are opening a text file or need to add new parameters to a  [!DNL .cfg] file.

   * **[!UICONTROL Open]** >  **[!UICONTROL folder]** if you want to open the folder which the file is located on your computer

1. 視需要編輯檔案，然後儲存檔案。

在[!DNL Profile Manager]中，請注意，您編輯的檔案的[!DNL User]列中的複選標籤已更改顏色。 這表示本機檔案現在與&#x200B;*描述檔名稱*&#x200B;資料夾中的版本不同。 如有必要，您可以將修訂版檔案發佈至描述檔，以供使用此描述檔的其他使用者使用。
