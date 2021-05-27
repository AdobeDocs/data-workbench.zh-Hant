---
description: 要使Report Portal能夠寫入包含驗證用戶所需資訊的資料庫，必須為資料庫設定正確的權限。
title: 設定資料庫的權限
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# 設定資料庫的權限{#set-permissions-for-the-database}

要使Report Portal能夠寫入包含驗證用戶所需資訊的資料庫，必須為資料庫設定正確的權限。

1. 在運行IIS的電腦上，導航到\*PortalName*\data\users.mdb。
1. 按一下右鍵&#x200B;**[!UICONTROL users.mdb]**&#x200B;檔案，然後選擇&#x200B;**[!UICONTROL Properties]**。
1. 在[!DNL Security]標籤的「組」或用戶名中，按一下「**[!UICONTROL Users]**」。
1. 在[!DNL Permission for User]中，在「寫入」行中，選擇&#x200B;**[!UICONTROL Allow]**。
1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;並關閉[!DNL Properties]對話框。
