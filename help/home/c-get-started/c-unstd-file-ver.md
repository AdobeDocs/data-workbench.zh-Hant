---
description: 「工作台」可讓您輕鬆判斷每個特定工作區的儲存位置，不論是在「資料工作台」伺服器、您的本機機器或兩者皆可。
solution: Analytics
title: 檔案版本修訂
topic: Data workbench
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 檔案版本修訂{#file-versioning}

「工作台」可讓您輕鬆判斷每個特定工作區的儲存位置，不論是在「資料工作台」伺服器、您的本機機器或兩者皆可。

## 識別檔案版本 {#section-d555c96b016344f19b356c12213dd2a9}

**伺服器**

伺服器工作區儲存在連線的資料工作台伺服器上，可供所有可存取此設定檔和標籤的使用者使用。 伺服器工作區會以單一縮圖顯示。

![](assets/wsp_thumb_server.png)

伺服器工作區預設會儲存在連線之資料工作台伺服器上「工作區」檔案夾內的適當子檔案夾中。

**本地**

本機工作區是伺服器工作區的本機版本。 本機工作區顯示為兩個重疊的縮圖。 最上方的縮圖一開始會被光暈所環繞，這表示伺服器工作區的本機最近變更。 這種光芒會隨著時間消散。

![](assets/wsp_thumb_local.png)

本機工作區預設會儲存在「資 [!DNL User\working profile name\Workspaces\tab] 料工作台」（或Insight）安裝目錄的名稱資料夾中。

>[!NOTE]
>
>當您擁有伺服器工作區的本地版本時，必須還原為伺服器版本，才能下載伺服器工作區的更新版本。 若要回復為伺服器版本而不進行本機變更，請在本機工作區的縮圖上按一下滑鼠右鍵，然後按一下 **[!UICONTROL Revert to server version]**。

**使用者**

用戶工作區是在上建立的工作區，僅存在於本地電腦上。 使用者工作區會以單一縮圖顯示，並在其後面加上空白工作區的虛線輪廓，表示連線的資料工作台伺服器上沒有來源工作區。

![](assets/wsp_thumb_user.png)

依預設，使用者工作區會儲存在Insight安裝目錄的User\*working profile name*\Workspaces\*tab name*資料夾中。
