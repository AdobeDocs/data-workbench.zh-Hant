---
description: 解除安裝data workbenchGeography的步驟。
title: 解除安裝 Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# 解除安裝 Data Workbench Geography{#uninstalling-data-workbench-geography}

解除安裝data workbenchGeography的步驟。

>[!NOTE]
>
>如果您使用Data Workbench [!DNL Geography]的設定檔在Data Workbench伺服器叢集上執行，請從叢集的主Data Workbench伺服器解除安裝[!DNL Geography]設定檔。

1. 使用下列步驟，針對您使用Data Workbench [!DNL Geography]的每個設定檔更新[!DNL profile.cfg]檔案。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵[!DNL profile.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。

   1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，從[!DNL Directories]向量中刪除[!DNL Geography]配置檔案條目。

   1. 如果您一直在使用資料服務，請從[!DNL Directories]向量中刪除[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]設定檔項目。

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

1. 從Data Workbench伺服器安裝目錄的Profiles資料夾中刪除Geography資料夾。
1. 如果您一直使用資料服務，請從Data Workbench伺服器安裝目錄的「設定檔」資料夾中刪除「IP地理情報」或「IP地理位置」資料夾。
1. 從Data Workbench伺服器安裝目錄的「查閱」資料夾中刪除Geography資料夾。
1. 如果您一直使用資料服務，請從Data Workbench伺服器安裝目錄的「查閱」資料夾中刪除「IP地理情報」或「IP地理位置」資料夾。
1. 如果您已建立新的地形影像，請從Data Workbench伺服器安裝目錄的「元件」資料夾中刪除[!DNL Terrain Images.cfg]檔案。
