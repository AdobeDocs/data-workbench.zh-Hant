---
description: 隨資料工作台提供的地理位置描述檔地理位置是內部描述檔，可為您的Adobe應用程式提供其他功能。
title: 安裝 Geography 設定檔
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# 安裝 Geography 設定檔{#installing-the-geography-profile}

隨資料工作台提供的地理位置描述檔地理位置是內部描述檔，可為您的Adobe應用程式提供其他功能。

與Adobe提供的所有其他內部配置檔案一樣，[!DNL Geography]配置檔案不應更改。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。

[!DNL Geography]描述檔包含數個轉換資料集，其中包含定義地理維度的檔案（位於[!DNL Dataset\Transformation\Geography]資料夾中）。 以下是轉換資料集的清單，其中包含隨[!DNL Geography]配置檔案提供的檔案：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

每個檔案都為它定義的擴展維命名。 另一個檔案[!DNL IPLookup.cfg]定義了幾個地理資料欄位，這些欄位用於定義其他轉換資料集中的維，包括檔案。

有關轉換資料集包括檔案的資訊，請參見&#x200B;*資料集配置指南*。

**若要在資料工 [!DNL Geography] 作台伺服器上安裝描述檔**

>[!NOTE]
>
>以下安裝說明假設您已安裝資料工作台，並已建立資料工作台與您要安裝資料工作台[!DNL Geography]之資料工作台伺服器之間的連線。 如果您尚未這樣做，請參閱&#x200B;*Data Workbench使用手冊*。

1. 從由Adobe提供給您的[!DNL .zip]檔案中開啟Profiles資料夾。
1. 將[!DNL Geography]資料夾複製至資料工作台伺服器安裝目錄中的Profiles資料夾。 您希望資料工作台伺服器上的[!DNL ...\Profiles\Geography]資料夾最後會出現，如下列範例所示。 「配置式」資料夾中其他資料夾的名稱可能與顯示的資料夾名稱不同。

   ![步驟資訊](assets/Geo_installProfiles_dir.png)

1. 使用下列步驟更新您要使用資料工作台[!DNL Geography]的每個描述檔的[!DNL profile.cfg]檔案。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵[!DNL profile.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。

   1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]視窗中，以滑鼠右鍵按一下&#x200B;**[!UICONTROL Directories]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱：[!DNL Geography]。
   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案（包括[!DNL Geography]配置檔案）中，因為在安裝這些配置檔案的更新時，將覆蓋您所做的更改。
