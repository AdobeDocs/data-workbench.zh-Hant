---
description: 您可以使用「描述檔管理員」來下載您要修改的檔案。
solution: Analytics
title: 修改用戶配置檔案中的本地檔案
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改用戶配置檔案中的本地檔案{#modify-local-files-in-the-user-profile}

您可以使用「描述檔管理員」來下載您要修改的檔案。

您可能想要下載檔案以原始檔案版本覆寫現有的本機檔案，或開啟、檢視和修改無法從工作區功能表存取的檔案。

**下載檔案**

1. 在中， [!DNL Profile Manager]開啟必要的資料夾和子資料夾以找到要下載的檔案。
1. 按一下右鍵檔案名稱旁的複選標籤，然後按一下 **[!UICONTROL Make Local]**。

   >[!NOTE]
   >
   >配置( [!DNL .cfg])、維度( [!DNL .dim])和量度( [!DNL .metric])檔案可直接在描述檔資料夾中編輯並儲存至伺服器，而不需將它們設為本機，並個別儲存至伺服器。 只需按一下右鍵檔案名稱旁的複選標籤，然後按一下工作 **[!UICONTROL Open]** 站中 **的>**。

將檔案下載到本地電腦後，列中會出現複選標籤，這表示該檔案的本地副本駐留在電腦上的User\*profile name*資料夾中。 [!DNL User] 請注意，複選標籤與描述檔名稱欄中的複選標籤 *顏色相* 同。 這表示本機檔案與描述檔名稱資料夾中的檔案具有相同的「修改日 *期* 」。

**要修改檔案**

1. 按一下右鍵列中檔案名旁的複選標 [!DNL User] 記。
1. 根據您要編輯檔案的方式，按一下下列其中一個功能表選項：

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** if you are editing a file [!DNL .vw] or a [!DNL .cfg] file in a workspace.

   * **開啟** > **in vw。 編輯器**如果您正在編輯。vw檔案以添加新參數。

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** if you are opening a text file or need to add new parameters to a [!DNL .cfg] file.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** if you want to open the folder which the file is located on your computer

1. 視需要編輯檔案，然後儲存檔案。

在中， [!DNL Profile Manager]請注意，您編輯的檔案的 [!DNL User] 列中的複選標籤已更改顏色。 這表示本機檔案現在與描述檔名稱資料夾中的版 *本不同* 。 如有必要，您可以將修訂版檔案發佈至描述檔，以供使用此描述檔的其他使用者使用。
