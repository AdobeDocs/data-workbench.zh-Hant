---
description: 在控制面板可以操作之前，必須允許它訪問SQL Server。
solution: Analytics
title: 配置SQL Server
topic: Data workbench
uuid: bdd5f9f5-a69f-4001-9f80-901bd7eae129
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置SQL Server{#configuring-the-sql-server}

在控制面板可以操作之前，必須允許它訪問SQL Server。

1. 以管理員身份開啟SQL Management Studio。
1. 按一下右鍵並選擇以添加新 **[!UICONTROL Logins]** 登錄 **[!UICONTROL New Login]**。
1. 輸入完整的應用程式池標識名。

   預設情況下，應用程式池標識以應用程式池命名。 如果您選 `dashboard`擇，則會命名身份 `IIS AppPool\dashboard`。 1.選 **[!UICONTROL Server Roles]** 擇並檢查 **[!UICONTROL dbcreator]** 角色。
1. Click **[!UICONTROL OK]** to add the new user.
