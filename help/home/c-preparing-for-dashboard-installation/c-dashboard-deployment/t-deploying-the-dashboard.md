---
description: 在IIS中部署控制面板的步驟。
solution: Analytics
title: 部署儀表板
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 部署儀表板{#deploying-the-dashboard}

在IIS中部署控制面板的步驟。

1. 建立安裝資料夾以安裝控制面板，例如 [!DNL c:\inetpub\wwwroot\dashboard]。
1. 在IIS中建立控制面板的應用程式池。
1. 開啟IIS Manager Console。
1. 前往 **[!UICONTROL Application Pools]** 。
1. 在右側的菜單中選[!UICONTROL Add Application Pool…]**[!UICONTROL Actions]** 擇****。
1. 在表 **[!UICONTROL Add Application Pool]** 單中，使用儀表板作為名稱，並選擇。NET Framework v.4.0.xxxxxx作為。NET Framework版本。
1. 將其他欄位保留為預設欄位，然 **[!UICONTROL OK]** 後按一下建立應用程式池。
1. 部署控制面板應用程式。
1. 開啟IIS Manager Console。
1. 展開 **[!UICONTROL Default Web Site]**，您應該會看到您在c:\inetpub\wwwroot\dashboard by default中建立的檔案夾。
1. 按一下右鍵資料夾並選擇 **[!UICONTROL Convert to Application]**。
1. 選取在步驟2中建立的**[!UICONTROL Application Pool]**（例如「儀表板」）。
1. 在下 **[!UICONTROL Sites]**&#x200B;方，以滑鼠右鍵按一下您要部署的網站（例如「預設網站」）。
1. 選擇 **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. 瀏覽並選取Adobe提供的控制面板部署檔案。
1. 按兩 **[!UICONTROL Next]** 下以繼續進入「輸入應用程式資訊」畫面。
1. 從此螢幕中，您可以選擇自訂控制面板部署。
1. 對於 **[!UICONTROL Application Path]**，輸入先前選擇的資料夾名稱。
1. 在下 **[!UICONTROL Disable Automatic Database Upgrade]**，輸 `False`入，因為這是新安裝。
1. 視需要自訂您的連線字串。 例如：

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. 按一下 **[!UICONTROL Next]** 此按鈕，IIS將開始安裝該應用程式。
1. 安裝完成後，安裝日誌中應該不會出現任何錯誤。
