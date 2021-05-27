---
description: 在IIS中部署控制面板的步驟。
title: 部署控制面板
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# 部署控制面板{#deploying-the-dashboard}

在IIS中部署控制面板的步驟。

1. 建立安裝資料夾以安裝控制面板，例如[!DNL c:\inetpub\wwwroot\dashboard]。
1. 在IIS中建立控制面板的應用程式池。
1. 開啟IIS Manager控制台。
1. 前往 **[!UICONTROL Application Pools]** 。
1. 在右側的&#x200B;**[!UICONTROL Actions]**&#x200B;功能表中選擇**[!UICONTROL Add Application Pool…]**。
1. 在&#x200B;**[!UICONTROL Add Application Pool]**&#x200B;表單中，使用該名稱的儀表板，然後選擇.NET Framework v.4.0.xxxxx作為.NET Framework版本。
1. 保留其他欄位為預設欄位，然後按一下&#x200B;**[!UICONTROL OK]**&#x200B;建立應用程式池。
1. 部署儀表板應用程式。
1. 開啟IIS Manager控制台。
1. 展開&#x200B;**[!UICONTROL Default Web Site]**，應該會看到您在c:\inetpub\wwwroot\dashboard by default中建立的資料夾。
1. 按一下右鍵該資料夾並選擇&#x200B;**[!UICONTROL Convert to Application]**。
1. 選取在步驟2中建立的**[!UICONTROL Application Pool]**（例如「控制面板」）。
1. 在&#x200B;**[!UICONTROL Sites]**&#x200B;下，按一下右鍵要部署的網站（例如「預設網站」）。
1. 選擇 **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. 瀏覽並選擇由Adobe提供的儀表板部署檔案。
1. 按兩下&#x200B;**[!UICONTROL Next]**&#x200B;以繼續進入「輸入應用程式資訊」螢幕。
1. 在此畫面中，您可以選擇自訂控制面板部署。
1. 對於&#x200B;**[!UICONTROL Application Path]**，輸入以前選擇的資料夾名稱。
1. 在&#x200B;**[!UICONTROL Disable Automatic Database Upgrade]**&#x200B;下，輸入`False`，因為這是新安裝。
1. 視需要自訂連線字串。 例如：

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. 按一下&#x200B;**[!UICONTROL Next]** ,IIS將開始安裝該應用程式。
1. 安裝完成後，安裝記錄中應該不會出現任何錯誤。
