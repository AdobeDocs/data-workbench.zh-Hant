---
description: 解除安裝資料工作台的步驟地理位置。
title: 解除安裝 Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# 解除安裝 Data Workbench Geography{#uninstalling-data-workbench-geography}

解除安裝資料工作台的步驟地理位置。

>[!NOTE]
>
>如果您使用的資料工作台[!DNL Geography]設定檔在資料工作台伺服器叢集上執行，請從叢集的主資料工作台伺服器解除安裝[!DNL Geography]設定檔。

1. 使用下列步驟更新您使用資料工作台[!DNL Geography]的每個描述檔的[!DNL profile.cfg]檔案。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵[!DNL profile.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。

   1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，從[!DNL Directories]向量中刪除[!DNL Geography]配置檔案條目。

   1. 如果您使用過資料服務，請從[!DNL Directories]向量中刪除[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]描述檔項目。

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。

1. 從資料工作台伺服器安裝目錄的「設定檔」檔案夾中刪除「地理」檔案夾。
1. 如果您使用資料服務，請從資料工作台伺服器安裝目錄的「設定檔」檔案夾中，刪除「IP地理智慧」或「IP地理位置」檔案夾。
1. 從資料工作台伺服器安裝目錄的「查閱」資料夾中刪除「地理位置」資料夾。
1. 如果您使用資料服務，請從資料工作台伺服器安裝目錄的「查閱」檔案夾中，刪除「IP地理智慧」或「IP地理位置」檔案夾。
1. 如果您建立了新的地形影像，請從資料工作台伺服器安裝目錄的「元件」檔案夾刪除[!DNL Terrain Images.cfg]檔案。
