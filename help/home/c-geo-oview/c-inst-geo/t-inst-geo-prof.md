---
description: 隨Data WorkbenchGeography提供的Geography設定檔是內部設定檔，可為您的Adobe應用程式提供額外功能。
title: 安裝 Geography 設定檔
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# 安裝 Geography 設定檔{#installing-the-geography-profile}

隨Data WorkbenchGeography提供的Geography設定檔是內部設定檔，可為您的Adobe應用程式提供額外功能。

與Adobe提供的所有其他內部設定檔一樣，[!DNL Geography]設定檔不應變更。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。

[!DNL Geography]設定檔包含定義地理維度的多個轉換資料集包含檔案（位於[!DNL Dataset\Transformation\Geography]資料夾中）。 以下是隨[!DNL Geography]設定檔提供的轉換資料集包含檔案的清單：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

每個檔案都會針對其定義的延伸維度命名。 另一個檔案[!DNL IPLookup.cfg]定義了幾個地理資料欄位，這些欄位用於定義其他轉換資料集包含檔案中的維度。

如需轉換資料集包含檔案的相關資訊，請參閱&#x200B;*資料集組態指南*。

**若要在Data  [!DNL Geography] Workbench伺服器上安裝設定檔**

>[!NOTE]
>
>下列安裝指示假設您已安裝data workbench，且已在您要安裝data workbench [!DNL Geography]的Data Workbench伺服器與Data Workbench伺服器之間建立連線。 若尚未這麼做，請參閱&#x200B;*Data Workbench使用手冊*。

1. 從[!DNL .zip]檔案中開啟Profiles資料夾(由Adobe提供)。
1. 將[!DNL Geography]資料夾複製到Data Workbench伺服器安裝目錄中的Profiles資料夾。 您想要在Data Workbench伺服器上顯示[!DNL ...\Profiles\Geography]資料夾，如下列範例所示。 「配置檔案」資料夾中其他資料夾的名稱可能與顯示的資料夾不同。

   ![步驟資訊](assets/Geo_installProfiles_dir.png)

1. 使用下列步驟，針對您要使用Data Workbench [!DNL Geography]的每個設定檔更新[!DNL profile.cfg]檔案。

   1. 開啟 [!DNL Profile Manager].
   1. 按一下右鍵[!DNL profile.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。

   1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，按一下右鍵&#x200B;**[!UICONTROL Directories]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱：[!DNL Geography]。
   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

      >[!NOTE]
      >
      >請勿將修改的配置檔案保存到Adobe提供的任何內部配置檔案（包括[!DNL Geography]配置檔案）中，因為安裝這些配置檔案的更新時，將覆蓋您的更改。
