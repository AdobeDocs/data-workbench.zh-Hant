---
description: 在控制面板可以運行之前，必須允許它訪問SQL Server。
title: 設定 SQL Server
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
exl-id: 16116cc8-f539-4cf0-ab1d-f2bddd39b38c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 8%

---

# 設定 SQL Server{#configuring-the-sql-server}

{{eol}}

在控制面板可以運行之前，必須允許它訪問SQL Server。

1. 以管理員身份開啟SQL Management Studio。
1. 按一下滑鼠右鍵以新增登入 **[!UICONTROL Logins]** 選取 **[!UICONTROL New Login]**.
1. 輸入完整的應用程式池標識名。

   預設情況下，應用程式池標識以應用程式池命名。 如果您選擇 `dashboard`，則會命名身分 `IIS AppPool\dashboard`. 1.選擇 **[!UICONTROL Server Roles]** 並檢查 **[!UICONTROL dbcreator]** 角色。
1. 按一下 **[!UICONTROL OK]** 以新增新使用者。
