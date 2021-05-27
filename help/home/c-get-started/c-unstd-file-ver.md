---
description: 操作台可讓您輕鬆判斷每個特定工作區的儲存位置，無論是位於Data Workbench伺服器、本機電腦，還是兩者皆可。
title: 檔案版本設定
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 2%

---

# 檔案版本設定{#file-versioning}

操作台可讓您輕鬆判斷每個特定工作區的儲存位置，無論是位於Data Workbench伺服器、本機電腦，還是兩者皆可。

## 識別檔案版本{#section-d555c96b016344f19b356c12213dd2a9}

**伺服器**

伺服器工作區儲存在連接的Data Workbench伺服器上，可供所有可存取此設定檔和索引標籤的使用者使用。 伺服器工作區顯示為單一縮圖。

![](assets/wsp_thumb_server.png)

伺服器工作區預設會儲存在所連接Data Workbench伺服器上Workspaces資料夾內的適當子資料夾中。

**本地**

本機工作區是伺服器工作區的本機版本。 本地工作區顯示為兩個重疊的縮圖。 頂端的縮圖一開始會被發光包圍，這表示最近已在本機對伺服器工作區進行變更。 這種光輝會隨著時間消散。

![](assets/wsp_thumb_local.png)

本機工作區預設會儲存在Data Workbench（或Insight）安裝目錄內的[!DNL User\working profile name\Workspaces\tab]名稱資料夾中。

>[!NOTE]
>
>當伺服器工作區的本地版本時，必須先恢復到伺服器版本，然後才能下載更新的伺服器工作區版本。 若要回復到伺服器版本而不進行本機變更，請以滑鼠右鍵按一下本機工作區的縮圖，然後按一下&#x200B;**[!UICONTROL Revert to server version]**。

**使用者**

用戶工作區是在上建立的工作區，僅存在於本地電腦上。 使用者工作區會顯示為單一縮圖，其後面有空白工作區的虛線外框，表示連線的Data Workbench伺服器上沒有來源工作區。

![](assets/wsp_thumb_user.png)

依預設，使用者工作區會儲存在Insight安裝目錄的User\*working profile name*\Workspaces\*tab name*資料夾中。
