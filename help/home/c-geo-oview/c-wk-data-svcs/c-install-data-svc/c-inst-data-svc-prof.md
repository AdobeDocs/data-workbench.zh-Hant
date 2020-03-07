---
description: 資料服務設定檔（IP地理智慧和IP地理位置）是內部設定檔，可為您的Adobe應用程式提供額外功能。
solution: Analytics
title: 安裝Data Service Profile
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安裝Data Service Profile{#installing-the-data-service-profile}

資料服務設定檔（IP地理智慧和IP地理位置）是內部設定檔，可為您的Adobe應用程式提供額外功能。

如同Adobe提供的所有其他內部設定檔，這些設定檔不應變更。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。

資料服務設定檔包含下列資料集，包括要安裝在資料工作台伺服器上的檔案：

* **描述檔\*描述檔名&#x200B;*稱\Dataset\Log Processing\Traffic\IP.cfg:**列出要從記錄處理傳遞至轉換的c-ip欄位。
* **描述檔\*描述檔名稱&#x200B;*\Dataset\Transformation\Geography\IPLookup.cfg:**定義IPLookup轉換，使用提供的IP地理智慧或IP地理位置查閱檔案產生數個地理資料欄位。

有關轉換資料集包括檔案的資訊，請參 *閱Dataset Configuration Guide*。

此外，每個資料服務描述檔都會提供一個名為的元素點層檔案 [!DNL IP Coordinates.layer]。 此圖層檔案可讓您使用IP位址動態地映射資料集在全球的位置。 安裝後，該層將儲存在資料工作台伺服器安裝目錄的Profiles\*data service name*\Maps資料夾中。

文 [!DNL IP Coordinates.layer] 件參照「坐標」(Coordinates)尺寸，該尺寸在隨配置檔案提供的 [!DNL Coordinates.cfg] 檔案中定義， [!DNL Geography] 並位於Dataset\Transformation\Geography folder目錄中。 在資料集中定義的座標維度，每個元素都會使用元素中包含的緯度和經度資訊，對應至地球。 有關使用動態點的元素點層的詳細資訊，請參 [閱使用動態點定義元素點層](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)。

>[!NOTE]
>
>如果您在5.1版之前安裝了IP地理情報和IP地理位置資料服務，您的元素點層檔案會參照查閱檔案，而非使用動態點。 每個層檔案都引用IP地理代碼查找檔案和IP地理代碼維。 「IP地理碼」查閱檔案包含IP地理碼（根據IP位址的地理位置）清單，以及每個地理碼的經緯度。 在資料集中定義的IP地理代碼維度的每個元素，都會使用IP地理代碼查閱檔案中該IP地理代碼所列的經緯度，在全球上進行映射。

層檔案的名稱及其引用的檔案對於每個資料服務都不同：

* 此 [!DNL IP Geocodes D.layer] 檔案會與IP地理智慧(Digital Envoy)設定檔一起安裝。 此元素點圖層會參照 [!DNL IP Geocodes D yyyymmdd.txt] 查閱檔案（您需要定期更新）和IP地理代碼D維度。

* 該 [!DNL IP Geocodes Q.layer] 檔案隨IP地理位置(Quova)配置檔案一起安裝。 此元素點圖層會參 [!DNL IP Geocodes Q yyyymmdd.txt] 照查閱檔案（您需要定期更新）和IP地理代碼Q維度。

有關使用查找檔案的元素點層的詳細資訊，請參 [閱定義元素點層引用查找檔案](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)。

## 若要安裝IP地理智慧或IP地理位置設定檔 {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>以下安裝說明假設您已安裝資料工作台，並已建立資料工作台與您要安裝資料工作台的資料工作台伺服器之間的連線 [!DNL Geography]。 如果您尚未這麼做，請參閱「資 *料工作台使用指南」*。

1. 從您從Adobe收到的檔 [!DNL .zip] 案中開啟「設定檔」檔案夾。
1. 將「IP地理智慧」或「IP地理位置」檔案夾複製至資料工作台伺服器安裝目錄中的「設定檔」檔案夾。 你最後想得到……\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example。 資料夾中其他資料夾的名稱 [!DNL Profiles] 可能與顯示的資料夾不同。

   ![](assets/Geo_installProfiles_dirIP.png)

1. 使用以下步驟更新 [!DNL profile.cfg] 要使用或配置檔案的每個配置檔案 [!DNL IP Geo-intelligence] 的文 [!DNL IP Geo-location] 件。

   1. 開啟 **[!UICONTROL Profile Manager]**.
   1. 按一下右鍵旁邊的複選標 [!DNL profile.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。

   1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 出現 [!DNL profile.cfg] 窗口。

   1. 在視窗 [!DNL profile.cfg]中，按一下滑鼠右鍵 **[!UICONTROL Directories]** 並按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

      要將新目錄添加到目錄清單的末尾，請按一下右鍵清單中最後一個目錄的編號或名稱，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Directory]**。

   1. 鍵入新目錄的名稱：或 [!DNL IP Geo-intelligence] 者我 [!DNL P Geo-location]。

   1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。

   1. 在中， [!DNL Profile Manager]按一下右鍵列中的複選 [!DNL profile.cfg] 標籤 [!DNL User] ，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*。

>[!NOTE]
>
>請勿將修改過的設定檔儲存至Adobe提供的任何內部設定檔(包括 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 設定檔)，因為當您安裝這些設定檔的更新時，會覆寫您的變更。

