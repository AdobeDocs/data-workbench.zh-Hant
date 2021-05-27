---
description: 資料服務設定檔（IP地理情報和IP地理位置）是內部設定檔，可為您的Adobe應用程式提供額外功能。
title: 安裝資料服務設定檔
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# 安裝資料服務設定檔{#installing-the-data-service-profile}

資料服務設定檔（IP地理情報和IP地理位置）是內部設定檔，可為您的Adobe應用程式提供額外功能。

與Adobe提供的所有其他內部設定檔一樣，這些設定檔不應變更。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。

資料服務設定檔包含下列資料集，包括要安裝在Data Workbench伺服器上的檔案：

* **設定檔\*設定檔名稱&#x200B;*\Dataset\Log Processing\Traffic\IP.cfg:**列出要從記錄處理傳遞至轉換的c-ip欄位。
* **設定檔\*設定檔名稱&#x200B;*\Dataset\Transformation\Geography\IPLookup.cfg:**定義IPLookup轉換，使用提供的IP地理情報或IP地理位置查閱檔案產生多個地理資料欄位。

如需轉換資料集包含檔案的相關資訊，請參閱&#x200B;*資料集組態指南*。

此外，每個資料服務配置檔案還為您提供一個名為[!DNL IP Coordinates.layer]的元素點層檔案。 此層檔案可讓您使用IP位址動態對應資料集在全球的位置。 安裝後，該層儲存在Data Workbench伺服器安裝目錄內的Profiles\*data service name*\Maps資料夾中。

[!DNL IP Coordinates.layer]檔案引用了坐標維，該維在隨[!DNL Geography]配置檔案提供的[!DNL Coordinates.cfg]檔案中定義，位於Dataset\Transformation\Geography folder中。 資料集中定義之「座標」維度的每個元素，都會使用該元素中包含的經緯度資訊，在地球上對應。 有關使用動態點的元素點層的詳細資訊，請參閱[使用動態點定義元素點層](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

>[!NOTE]
>
>如果您安裝的IP地理情報和IP地理位置資料服務版本早於5.1版，則您的元素點層檔案會參考查閱檔案，而非使用動態點。 每個層檔案都會參考IP地理碼查閱檔案和IP地理碼維度。 「IP地理碼」查閱檔案包含IP地理碼（根據IP位址的地理位置）清單，以及每個地理碼的經緯度。 資料集中定義之IP地理碼維度的每個元素，都會透過IP地理碼查閱檔案中該IP地理碼所列的經緯度，在地球上對應。

層檔案的名稱及其所引用的檔案對於每個資料服務都不同：

* [!DNL IP Geocodes D.layer]檔案會與IP地理情報(Digital Envoy)設定檔一起安裝。 此元素點層會參考[!DNL IP Geocodes D yyyymmdd.txt]查閱檔案（您需要定期更新）和IP地理代碼D維度。

* [!DNL IP Geocodes Q.layer]檔案隨IP地理位置(Quova)配置檔案一起安裝。 此元素點層會參考[!DNL IP Geocodes Q yyyymmdd.txt]查閱檔案（您需要定期更新）和IP地理碼Q維度。

有關使用查閱檔案的元素點層的詳細資訊，請參閱[定義參考查閱檔案的元素點層](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)。

## 安裝IP地理情報或IP地理位置配置檔案{#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>下列安裝指示假設您已安裝data workbench，且已在您要安裝data workbench [!DNL Geography]的Data Workbench與Data Workbench伺服器之間建立連線。 若尚未這麼做，請參閱&#x200B;*Data Workbench使用手冊*。

1. 從您從Adobe接收的[!DNL .zip]檔案中開啟Profiles資料夾。
1. 將IP地理情報或IP地理位置資料夾複製到Data Workbench伺服器安裝目錄中的設定檔資料夾。 你最後想要的是……\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example。 [!DNL Profiles]資料夾中其他資料夾的名稱可能與顯示的名稱不同。

   ![](assets/Geo_installProfiles_dirIP.png)

1. 使用下列步驟來更新每個要使用[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]配置檔案的[!DNL profile.cfg]檔案。

   1. 開啟 **[!UICONTROL Profile Manager]**.
   1. 按一下右鍵[!DNL profile.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。

   1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]視窗中，按一下右鍵&#x200B;**[!UICONTROL Directories]** ，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱：[!DNL IP Geo-intelligence]或I [!DNL P Geo-location]。

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

>[!NOTE]
>
>請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔（包括[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]設定檔），因為您在安裝這些設定檔的更新時，變更會遭到覆寫。
