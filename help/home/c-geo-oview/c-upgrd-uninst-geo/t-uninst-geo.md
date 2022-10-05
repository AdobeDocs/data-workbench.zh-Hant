---
description: 解除安裝data workbenchGeography的步驟。
title: 解除安裝 Data Workbench Geography
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 4%

---

# 解除安裝 Data Workbench Geography{#uninstalling-data-workbench-geography}

{{eol}}

解除安裝data workbenchGeography的步驟。

>[!NOTE]
>
>如果您使用Data Workbench的設定檔 [!DNL Geography] 在data workbench伺服器叢集上執行，請解除安裝 [!DNL Geography] 設定檔（來自叢集中的主資料工作台伺服器）。

1. 使用下列步驟來更新 [!DNL profile.cfg] 您使用data workbench的每個設定檔的檔案 [!DNL Geography].

   1. 開啟 [!DNL Profile Manager].
   1. 以滑鼠右鍵按一下旁的核取記號 [!DNL profile.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。

   1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 此 [!DNL profile.cfg] 的上界。

   1. 在 [!DNL profile.cfg] ，刪除 [!DNL Geography] 設定檔項目 [!DNL Directories] 向量圖。

   1. 如果您一直在使用資料服務，請刪除 [!DNL IP Geo-intelligence] 或 [!DNL IP Geo-location] 設定檔項目 [!DNL Directories] 向量圖。

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL profile.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. 從Data Workbench伺服器安裝目錄的Profiles資料夾中刪除Geography資料夾。
1. 如果您一直使用資料服務，請從Data Workbench伺服器安裝目錄的「設定檔」資料夾中刪除「IP地理情報」或「IP地理位置」資料夾。
1. 從Data Workbench伺服器安裝目錄的「查閱」資料夾中刪除Geography資料夾。
1. 如果您一直使用資料服務，請從Data Workbench伺服器安裝目錄的「查閱」資料夾中刪除「IP地理情報」或「IP地理位置」資料夾。
1. 如果您建立了新的地形影像，請刪除 [!DNL Terrain Images.cfg] 檔案（位於data workbench伺服器安裝目錄的「元件」資料夾中）。
