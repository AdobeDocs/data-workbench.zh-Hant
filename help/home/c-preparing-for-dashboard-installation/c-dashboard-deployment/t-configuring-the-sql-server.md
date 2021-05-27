---
description: 在控制面板可以運行之前，必須允許它訪問SQL Server。
title: 設定 SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# 設定 SQL Server{#configuring-the-sql-server}

在控制面板可以運行之前，必須允許它訪問SQL Server。

1. 以管理員身份開啟SQL Management Studio。
1. 按一下右鍵&#x200B;**[!UICONTROL Logins]**&#x200B;並選擇&#x200B;**[!UICONTROL New Login]**&#x200B;以添加新登錄。
1. 輸入完整的應用程式池標識名。

   預設情況下，應用程式池標識以應用程式池命名。 如果選擇`dashboard`，則標識將命名為`IIS AppPool\dashboard`。 1.選擇&#x200B;**[!UICONTROL Server Roles]**&#x200B;並檢查&#x200B;**[!UICONTROL dbcreator]**&#x200B;角色。
1. 按一下&#x200B;**[!UICONTROL OK]**&#x200B;以新增使用者。
