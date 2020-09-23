---
description: 解除安裝Insight Server、Transform或Repeater的指示。
solution: Analytics
title: 解除安裝軟體
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---


# 解除安裝軟體{#uninstalling-your-software}

解除安裝Insight Server、Transform或Repeater的指示。

## 解除安裝Insight Server Adobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. 註銷 [!DNL Insight Server] Windows服務。

   1. 開啟命令提示符，並導航到所安裝資料夾中的bin子目錄 [!DNL Insight Server]。

      範例：[!DNL C:\Adobe\Server\bin]

   1. 在命令提示符下，執行以下命令以停止Microsoft Windows下的服務並將其註銷：

      ```
      InsightServer64.exe /unregserver
      ```

1. 刪除安 [!DNL Insight Server] 裝目錄。

## 卸載轉換 {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 請依照下列步驟，更新 [!DNL profile.cfg] 您使用之每個描述檔的檔案 [!DNL Transform]。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵旁邊的複選標 [!DNL profile.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。

   1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Insight]**。 出現 [!DNL profile.cfg] 窗口。

   1. 在窗口 [!DNL profile.cfg] 中，從「目錄」向 [!DNL Transform] 量中刪除配置檔案條目。

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Profile Manager]按一下右鍵列中的複選 [!DNL profile.cfg] 標籤 [!DNL User] ，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

1. 從安裝目 [!DNL Transform] 錄中的資 [!DNL Profiles] 料夾刪除資 [!DNL Insight Server] 料夾。

## 解除安裝中繼器 {#section-2f94141d956749d88f549dbea26e5272}

1. 註銷 [!DNL Repeater] Windows服務。

   1. 開啟命令提示符，並導航到所安裝資料夾中的bin子目錄 [!DNL Repeater]。

      範例：[!DNL D:\Adobe\Repeater\bin]

   1. 在命令提示符下，執行以下命令以停止Microsoft Windows下的服務並將其註銷：

      ```
      InsightServer64.exe /unregserver
      ```

1. 刪除安 [!DNL Repeater] 裝目錄。

