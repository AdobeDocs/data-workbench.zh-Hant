---
description: 解除安裝Insight Server、Transform或Repeater的指示。
title: 解除安裝軟體
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# 解除安裝軟體{#uninstalling-your-software}

解除安裝Insight Server、Transform或Repeater的指示。

## 卸載Insight ServerAdobe{#section-7d7befe672854df79bb6c28ec02f6670}

1. 註銷[!DNL Insight Server] Windows服務。

   1. 開啟命令提示符並導航到[!DNL Insight Server]所在資料夾中的bin子目錄。

      範例：[!DNL C:\Adobe\Server\bin]

   1. 在命令提示符下，執行以下命令以停止Microsoft Windows下的服務並將其註銷：

      ```
      InsightServer64.exe /unregserver
      ```

1. 刪除[!DNL Insight Server]安裝目錄。

## 卸載轉換{#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 使用以下步驟更新您使用[!DNL Transform]的每個配置檔案的[!DNL profile.cfg]檔案。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵[!DNL profile.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。

   1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，從目錄向量中刪除[!DNL Transform]配置檔案條目。

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。

1. 從[!DNL Insight Server]安裝目錄的[!DNL Profiles]資料夾刪除[!DNL Transform]資料夾。

## 解除安裝中繼器{#section-2f94141d956749d88f549dbea26e5272}

1. 註銷[!DNL Repeater] Windows服務。

   1. 開啟命令提示符並導航到[!DNL Repeater]所在資料夾中的bin子目錄。

      範例：[!DNL D:\Adobe\Repeater\bin]

   1. 在命令提示符下，執行以下命令以停止Microsoft Windows下的服務並將其註銷：

      ```
      InsightServer64.exe /unregserver
      ```

1. 刪除[!DNL Repeater]安裝目錄。
