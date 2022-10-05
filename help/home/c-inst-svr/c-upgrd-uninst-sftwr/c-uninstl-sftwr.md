---
description: 解除安裝Insight Server、轉換或中繼器的指示。
title: 解除安裝軟體
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# 解除安裝軟體{#uninstalling-your-software}

{{eol}}

解除安裝Insight Server、轉換或中繼器的指示。

## 解除安裝Insight ServerAdobe {#section-7d7befe672854df79bb6c28ec02f6670}

1. 註銷 [!DNL Insight Server] Windows服務。

   1. 開啟命令提示符，並導覽至安裝資料夾中的bin子目錄 [!DNL Insight Server].

      範例：[!DNL C:\Adobe\Server\bin]

   1. 在命令提示符下，執行以下命令以停止並註銷Microsoft Windows下的服務：

      ```
      InsightServer64.exe /unregserver
      ```

1. 刪除 [!DNL Insight Server] 安裝目錄。

## 解除安裝轉換 {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 使用下列步驟來更新 [!DNL profile.cfg] 檔案 [!DNL Transform].

   1. 開啟 [!DNL Profile Manager].
   1. 以滑鼠右鍵按一下旁的核取記號 [!DNL profile.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。

   1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. 此 [!DNL profile.cfg] 的上界。

   1. 在 [!DNL profile.cfg] ，刪除 [!DNL Transform] 目錄向量中的配置檔案條目。

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL profile.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. 刪除 [!DNL Transform] 資料夾 [!DNL Profiles] 檔案夾 [!DNL Insight Server] 安裝目錄。

## 解除安裝中繼器 {#section-2f94141d956749d88f549dbea26e5272}

1. 註銷 [!DNL Repeater] Windows服務。

   1. 開啟命令提示符，並導覽至安裝資料夾中的bin子目錄 [!DNL Repeater].

      範例：[!DNL D:\Adobe\Repeater\bin]

   1. 在命令提示符下，執行以下命令以停止並註銷Microsoft Windows下的服務：

      ```
      InsightServer64.exe /unregserver
      ```

1. 刪除 [!DNL Repeater] 安裝目錄。
