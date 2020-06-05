---
description: 最後一個步驟是首次執行控制面板以允許其初始化。
solution: Analytics
title: 初始化控制面板
topic: Data workbench
uuid: 847ba63e-29d8-4950-aa74-22d825388e2b
translation-type: tm+mt
source-git-commit: 4b39a42285c39e26f097b91309c269c05a9475bd
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 1%

---


# 初始化控制面板{#initializing-the-dashboard}

最後一個步驟是首次執行控制面板以允許其初始化。

1. 開啟網頁瀏覽器並輸入新部署網站的URL(例如http://localhost/dashboard)。
1. 首次連接將設定資料庫表，因此可能會遇到輕微延遲。
1. 初始登錄憑據為：

   * **[!UICONTROL Username]**: admin
   * **[!UICONTROL Password]**: password

1. 在您第一次登入時，請前往 **[!UICONTROL User]** > **[!UICONTROL Account Settings]** ，然後選 **[!UICONTROL Change Password]** 取以變更管理員密碼。

控制面板安裝現已完成。 如果您尚未使用，請使用本指南「準備資料工作台」一節中詳細說明的指示，以設定您與資料工作台伺服器的通訊，並管理使用者和群組。

>[!NOTE]
>
>在安裝路徑的目錄中可找到儀表板 [!DNL logs] 錯誤和審計日誌。

>[!NOTE]
>
>如果需要將應用程式池標識更改為其他帳戶，請確保授予對資料庫的訪問權，並授予對安裝路徑中資料夾的標識讀 [!DNL logs] /寫訪問權限。

>[!NOTE]
>
>如果您需要更改資料庫的連接字串，只需使用編輯值即可 **[!UICONTROL IIS Management Console]**。
