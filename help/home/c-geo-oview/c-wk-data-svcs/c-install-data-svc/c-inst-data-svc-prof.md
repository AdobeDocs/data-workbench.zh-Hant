---
description: 資料服務設定檔（IP地理智慧和IP地理位置）是內部設定檔，可為您的Adobe應用程式提供額外功能。
title: 安裝資料服務設定檔
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
exl-id: 51d080bb-f874-426c-91ea-3912ffd38419
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 1%

---

# 安裝資料服務設定檔{#installing-the-data-service-profile}

資料服務設定檔（IP地理智慧和IP地理位置）是內部設定檔，可為您的Adobe應用程式提供額外功能。

與Adobe提供的所有其他內部配置檔案一樣，這些配置檔案不應更改。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。

資料服務設定檔包含下列資料集，包括要安裝在資料工作台伺服器上的檔案：

* **描述檔\*描述檔名&#x200B;*稱\Dataset\Log Processing\Traffic\IP.cfg:**列出要從記錄處理傳遞至轉換的c-ip欄位。
* **描述檔\*描述檔名稱&#x200B;*\Dataset\Transformation\Geography\IPLookup.cfg:**定義IPLookup轉換，使用提供的IP地理智慧或IP地理位置查閱檔案產生數個地理資料欄位。

有關轉換資料集包括檔案的資訊，請參見&#x200B;*資料集配置指南*。

此外，每個資料服務配置檔案還為您提供一個名為[!DNL IP Coordinates.layer]的元素點層檔案。 此圖層檔案可讓您使用IP位址動態地映射資料集在全球的位置。 安裝後，該層將儲存在資料工作台伺服器安裝目錄的Profiles\*data service name*\Maps資料夾中。

[!DNL IP Coordinates.layer]檔案引用坐標尺寸，該尺寸在[!DNL Coordinates.cfg]檔案中定義，該檔案隨[!DNL Geography]配置檔案提供，位於Dataset\Transformation\Geography folder檔案中。 在資料集中定義的座標維度，每個元素都會使用元素中包含的緯度和經度資訊，對應至地球。 有關使用動態點的元素點層的詳細資訊，請參閱[使用動態點定義元素點層](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

>[!NOTE]
>
>如果您在5.1版之前安裝了IP地理情報和IP地理位置資料服務，您的元素點層檔案會參照查閱檔案，而非使用動態點。 每個層檔案都引用IP地理代碼查找檔案和IP地理代碼維。 「IP地理碼」查閱檔案包含IP地理碼（根據IP位址的地理位置）清單，以及每個地理碼的經緯度。 在資料集中定義的IP地理代碼維度的每個元素，都會使用IP地理代碼查閱檔案中該IP地理代碼所列的經緯度，在全球上進行映射。

層檔案的名稱及其引用的檔案對於每個資料服務都不同：

* [!DNL IP Geocodes D.layer]檔案會與IP地理智慧(Digital Envoy)設定檔一起安裝。 此元素點層會參照[!DNL IP Geocodes D yyyymmdd.txt]查閱檔案（您需要定期更新）和IP地理代碼D維度。

* [!DNL IP Geocodes Q.layer]檔案隨IP地理位置(Quova)配置檔案一起安裝。 此元素點層會參照[!DNL IP Geocodes Q yyyymmdd.txt]查閱檔案（您需要定期更新）和IP Geocode Q維度。

有關使用查找檔案的元素點層的詳細資訊，請參閱[定義元素點層引用查找檔案](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)。

## 要安裝IP地理智慧或IP地理位置配置檔案{#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>以下安裝說明假設您已安裝資料工作台，並已建立資料工作台與您要安裝資料工作台[!DNL Geography]之資料工作台伺服器之間的連線。 如果您尚未這樣做，請參閱&#x200B;*Data Workbench使用手冊*。

1. 從您從Adobe收到的[!DNL .zip]檔案開啟Profiles資料夾。
1. 將「IP地理智慧」或「IP地理位置」檔案夾複製至資料工作台伺服器安裝目錄中的「設定檔」檔案夾。 你最後想得到……\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example。 [!DNL Profiles]資料夾中其他資料夾的名稱可能與顯示的資料夾名稱不同。

   ![](assets/Geo_installProfiles_dirIP.png)

1. 使用以下步驟可以更新每個要使用[!DNL IP Geo-intelligence]或[!DNL IP Geo-location]配置檔案的配置檔案的[!DNL profile.cfg]檔案。

   1. 開啟 **[!UICONTROL Profile Manager]**.
   1. 按一下右鍵[!DNL profile.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。

   1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]視窗中，以滑鼠右鍵按一下&#x200B;**[!UICONTROL Directories]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱：[!DNL IP Geo-intelligence]或I [!DNL P Geo-location]。

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL profile.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。

>[!NOTE]
>
>請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案（包括[!DNL IP Geo-location]或[!DNL IP Geo-intelligence]配置檔案），因為在安裝這些配置檔案的更新時將覆蓋您所做的更改。
