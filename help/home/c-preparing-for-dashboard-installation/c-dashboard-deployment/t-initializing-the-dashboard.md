---
description: 最後一步是首次執行控制面板，以允許其初始化。
title: 初始化控制面板
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
exl-id: 47098d73-d8c4-4d14-964f-108a731d3733
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 4%

---

# 初始化控制面板{#initializing-the-dashboard}

最後一步是首次執行控制面板，以允許其初始化。

1. 開啟網頁瀏覽器，然後輸入新部署網站的URL(例如https://localhost/dashboard)。
1. 首次連接將設定資料庫表，因此可能會遇到一些延遲。
1. 初始登錄憑據為：

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 首次登錄時，請轉至&#x200B;**[!UICONTROL User]** > **[!UICONTROL Account Settings]**&#x200B;並選擇&#x200B;**[!UICONTROL Change Password]**&#x200B;以更改管理員密碼。

控制面板安裝現在已完成。 如果您尚未完成，請使用本指南的準備Data Workbench一節中詳細說明的指示，設定您與Data Workbench伺服器的通訊，以及管理使用者和群組。

>[!NOTE]
>
>在安裝路徑的[!DNL logs]目錄中可找到控制面板錯誤和稽核記錄。

>[!NOTE]
>
>如果需要將應用程式池標識更改為其他帳戶，請確保授予對資料庫的訪問權，並授予對安裝路徑中[!DNL logs]資料夾的標識讀/寫訪問權限。

>[!NOTE]
>
>如果您需要更改資料庫的連接字串，只需使用&#x200B;**[!UICONTROL IIS Management Console]**&#x200B;編輯值即可。
