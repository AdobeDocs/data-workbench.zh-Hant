---
description: 隨Data WorkbenchGeography提供的Geography設定檔是內部設定檔，可為您的Adobe應用程式提供額外功能。
title: 安裝 Geography 設定檔
uuid: afc0699d-e58b-481b-a3f2-ab6d6998bdd8
exl-id: 9ab07fd4-d6e7-495e-ba34-04e53c9b0aa3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 2%

---

# 安裝 Geography 設定檔{#installing-the-geography-profile}

{{eol}}

隨Data WorkbenchGeography提供的Geography設定檔是內部設定檔，可為您的Adobe應用程式提供額外功能。

如同Adobe提供的所有其他內部設定檔， [!DNL Geography] 設定檔不應變更。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。

此 [!DNL Geography] 設定檔包含數個轉換資料集包含檔案(位於 [!DNL Dataset\Transformation\Geography] 資料夾)來定義地理維度。 以下是隨提供的轉換資料集包含檔案清單 [!DNL Geography] 設定檔：

* [!DNL City.cfg]
* [!DNL Coordinates.cfg]
* [!DNL Country.cfg]
* [!DNL DMA.cfg]
* [!DNL Domain.cfg]

每個檔案都會針對其定義的延伸維度命名。 另一個檔案， [!DNL IPLookup.cfg]，會定義多個地理資料欄位，這些欄位用於定義其他轉換資料集包含檔案中的維度。

如需轉換資料集包含檔案的相關資訊，請參閱 *資料集組態指南*.

**若要安裝 [!DNL Geography] data workbench伺服器上的設定檔**

>[!NOTE]
>
>下列安裝指示假設您已安裝data workbench，且已在Data Workbench與您要安裝Data Workbench的Data Workbench伺服器之間建立連線 [!DNL Geography]. 若尚未這麼做，請參閱 *Data Workbench使用手冊*.

1. 從 [!DNL .zip] 檔案(由Adobe提供)。
1. 複製 [!DNL Geography] 資料夾，移至data workbench伺服器安裝目錄中的「設定檔」資料夾。 你最後想用 [!DNL ...\Profiles\Geography] 資料夾，如下列範例所示。 「配置檔案」資料夾中其他資料夾的名稱可能與顯示的資料夾不同。

   ![步驟資訊](assets/Geo_installProfiles_dir.png)

1. 使用下列步驟來更新 [!DNL profile.cfg] 檔案，以取得您要使用data workbench的每個設定檔 [!DNL Geography].

   1. 開啟 [!DNL Profile Manager].
   1. 以滑鼠右鍵按一下旁的核取記號 [!DNL profile.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。

   1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 此 [!DNL profile.cfg] 的上界。

   1. 在 [!DNL profile.cfg] 窗口，按一下右鍵 **[!UICONTROL Directories]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. 鍵入新目錄的名稱： [!DNL Geography].
   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL profile.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

      >[!NOTE]
      >
      >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔(包括 [!DNL Geography] 設定檔)，當您安裝這些設定檔的更新時，變更會遭到覆寫。
