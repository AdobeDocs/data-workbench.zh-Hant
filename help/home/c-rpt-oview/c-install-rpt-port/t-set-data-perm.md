---
description: 要使Report Portal能夠寫入包含驗證用戶所需資訊的資料庫，必須為資料庫設定正確的權限。
title: 設定資料庫的權限
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# 設定資料庫的權限{#set-permissions-for-the-database}

{{eol}}

要使Report Portal能夠寫入包含驗證用戶所需資訊的資料庫，必須為資料庫設定正確的權限。

1. 在運行IIS的電腦上，導航到\*PortalName*\data\users.mdb。
1. 以滑鼠右鍵按一下 **[!UICONTROL users.mdb]** 檔案和選取 **[!UICONTROL Properties]**.
1. 在 [!DNL Security] 頁簽，在組或用戶名中，按一下 **[!UICONTROL Users]**.
1. 在 [!DNL Permission for User]，在「寫入」行中，選擇 **[!UICONTROL Allow]**.
1. 按一下 **[!UICONTROL OK]** 然後關閉 [!DNL Properties] 對話框。
