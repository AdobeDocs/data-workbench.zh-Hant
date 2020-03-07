---
description: 解除安裝資料工作台的步驟地理位置。
solution: Analytics
title: 解除安裝資料工作台地理位置
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 解除安裝資料工作台地理位置{#uninstalling-data-workbench-geography}

解除安裝資料工作台的步驟地理位置。

>[!NOTE]
>
>如果您使用的資料工作台描述檔在資料工作台 [!DNL Geography] 伺服器叢集上執行，請從叢集的主資料工作台 [!DNL Geography] 伺服器解除安裝描述檔。

1. 使用下列步驟更新您 [!DNL profile.cfg] 使用資料工作台的每個描述檔的檔案 [!DNL Geography]。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵旁邊的複選標 [!DNL profile.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。

   1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 出現 [!DNL profile.cfg] 窗口。

   1. 在窗口 [!DNL profile.cfg] 中，從向量中刪 [!DNL Geography] 除配置檔案 [!DNL Directories] 條目。

   1. 如果您使用過資料服務，請從向量中刪 [!DNL IP Geo-intelligence] 除 [!DNL IP Geo-location] 或描述檔 [!DNL Directories] 項目。

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Profile Manager]按一下右鍵列中的複選 [!DNL profile.cfg] 標籤 [!DNL User] ，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

1. 從資料工作台伺服器安裝目錄的「設定檔」檔案夾中刪除「地理」檔案夾。
1. 如果您使用資料服務，請從資料工作台伺服器安裝目錄的「設定檔」檔案夾中，刪除「IP地理智慧」或「IP地理位置」檔案夾。
1. 從資料工作台伺服器安裝目錄的「查閱」資料夾中刪除「地理位置」資料夾。
1. 如果您使用資料服務，請從資料工作台伺服器安裝目錄的「查閱」檔案夾中，刪除「IP地理智慧」或「IP地理位置」檔案夾。
1. 如果您建立了新的地形影像，請從資料 [!DNL Terrain Images.cfg] 工作台伺服器安裝目錄的「元件」檔案夾中刪除檔案。
