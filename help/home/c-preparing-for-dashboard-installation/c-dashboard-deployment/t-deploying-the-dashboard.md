---
description: 在IIS中部署控制面板的步驟。
title: 部署控制面板
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# 部署控制面板{#deploying-the-dashboard}

{{eol}}

在IIS中部署控制面板的步驟。

1. 建立安裝資料夾以安裝控制面板，例如 [!DNL c:\inetpub\wwwroot\dashboard].
1. 在IIS中建立控制面板的應用程式池。
1. 開啟IIS Manager控制台。
1. 前往 **[!UICONTROL Application Pools]**。
1. 選擇**[!UICONTROL Add Application Pool…]**在 **[!UICONTROL Actions]** 菜單。
1. 在 **[!UICONTROL Add Application Pool]** 表單中，請使用控制面板作為名稱，然後選擇.NET Framework v.4.0.xxxxxx作為.NET Framework版本。
1. 保留其他欄位為預設欄位，然後按一下 **[!UICONTROL OK]** 建立應用程式池。
1. 部署儀表板應用程式。
1. 開啟IIS Manager控制台。
1. 展開 **[!UICONTROL Default Web Site]**，您應該會在c:\inetpub\wwwroot\dashboard by default中看到您建立的資料夾。
1. 以滑鼠右鍵按一下資料夾並選取 **[!UICONTROL Convert to Application]**.
1. 選取**[!UICONTROL Application Pool]**在步驟2中建立（例如「控制面板」）。
1. 在 **[!UICONTROL Sites]**，請以滑鼠右鍵按一下您要部署的網站（例如「預設網站」）。
1. 選擇 **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. 瀏覽並選擇由Adobe提供的儀表板部署檔案。
1. 按一下 **[!UICONTROL Next]** 前往「輸入應用程式資訊」螢幕兩次。
1. 在此畫面中，您可以選擇自訂控制面板部署。
1. 針對 **[!UICONTROL Application Path]**，輸入先前選取的資料夾名稱。
1. 在 **[!UICONTROL Disable Automatic Database Upgrade]**，輸入 `False`，因為這是新安裝。
1. 視需要自訂連線字串。 例如：

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. 按一下 **[!UICONTROL Next]** 和IIS將開始安裝應用程式。
1. 安裝完成後，安裝記錄中應該不會出現任何錯誤。
