---
description: 隨資料工作台提供的地理位置描述檔地理位置是內部描述檔，可為您的Adobe應用程式提供其他功能。
solution: Analytics
title: 安裝地理位置設定檔
topic: Data workbench
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝地理位置設定檔{#installing-the-geography-profile}

隨資料工作台提供的地理位置描述檔地理位置是內部描述檔，可為您的Adobe應用程式提供其他功能。

如同Adobe提供的所有其他內部設定檔， [!DNL Geography] 不應變更設定檔。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。

描述 [!DNL Geography] 檔包含數個轉換資料集，包括定義地理維度的檔 [!DNL Dataset\Transformation\Geography] 案（位於資料夾中）。 以下是轉換資料集的清單，其中包括隨配置檔案提供的 [!DNL Geography] 檔案：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

每個檔案都為它定義的擴展維命名。 另外一個檔案 [!DNL IPLookup.cfg]定義了幾個地理資料欄位，這些欄位用於定義其他轉換資料集中的維，包括檔案。

有關轉換資料集包括檔案的資訊，請參 *閱Dataset Configuration Guide*。

**若要在資料[!DNL Geography]工作台伺服器上安裝描述檔**

>[!NOTE]
>
>以下安裝說明假設您已安裝資料工作台，並已建立資料工作台與您要安裝資料工作台的資料工作台伺服器之間的連線 [!DNL Geography]。 如果您尚未這麼做，請參閱「資 *料工作台使用指南」*。

1. 從Adobe提供給您的檔 [!DNL .zip] 案中開啟「描述檔」檔案夾。
1. 將資料 [!DNL Geography] 夾複製至資料工作台伺服器安裝目錄的「設定檔」資料夾。 您希望資料工作台伺服 [!DNL ...\Profiles\Geography] 器上的資料夾最後會出現，如下列範例所示。 「配置式」資料夾中其他資料夾的名稱可能與顯示的資料夾名稱不同。

   ![步驟資訊](assets/Geo_installProfiles_dir.png)

1. 請使用下列步驟來更 [!DNL profile.cfg] 新您要使用資料工作台的每個描述檔的檔案 [!DNL Geography]。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵旁邊的複選標 [!DNL profile.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。

   1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 出現 [!DNL profile.cfg] 窗口。

   1. 在視窗 [!DNL profile.cfg] 中，以滑鼠右鍵按一 **[!UICONTROL Directories]** 下並按 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱： [!DNL Geography]。
   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Profile Manager]按一下右鍵列中的複選 [!DNL profile.cfg] 標籤 [!DNL User] ，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔（包括設定檔），因為當您安裝這些設定檔的更新時，會覆寫您的變更。 [!DNL Geography]

