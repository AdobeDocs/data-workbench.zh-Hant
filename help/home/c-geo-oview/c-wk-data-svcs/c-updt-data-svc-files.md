---
description: 如果您訂閱任一資料服務，您必須定期更新Adobe提供的資料服務檔案。
solution: Analytics
title: 更新資料服務檔案
topic: Data workbench
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 更新資料服務檔案{#updating-data-service-files}

如果您訂閱任一資料服務，您必須定期更新Adobe提供的資料服務檔案。

若要這麼做，您必須擁有資料工作台伺服器上檔案的存取權。

要載入 [!DNL IP Geo-location] 或數 [!DNL IP Geo-intelligence] 據檔案，必須完成以下過程。

## 取代資料檔案 {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. 在資料工作台的「 >」標 [!DNL Admin] 簽 [!DNL Dataset and Profile] 上，按一下縮 **[!UICONTROL Servers Manager]** 圖以開啟工作 [!DNL Servers Manager] 區。

1. 在視窗 [!DNL Servers Manager] 中，以滑鼠右鍵按一下您要載入檔案的資料工作台伺服器圖示，然後按一下 **[!UICONTROL Server Files]**。

1. 在欄 [!DNL Server Files Manager]中，按一下或的 **[!UICONTROL Temp]** 欄 **[!UICONTROL Lookups\IP Geo-location]** ，然後按一 **[!UICONTROL Lookups\IP Geo-intelligence]** 下> **[!UICONTROL Open]** &lt; *>**[!UICONTROL folder]***。

1. 將Adobe [!DNL .bin] 提供的資料檔案複製至Lookups\IP Geo-location或Lookups\IP Geo-intelligence資料夾視窗。
1. 在資料檔案的欄上按一下滑鼠右鍵，然後按一下> [!DNL Temp] &lt; **[!UICONTROL Save to]** >，將檔案儲存至資料工作台伺服器 ***[!UICONTROL server name]***。

   如果您正在運行群集，請將檔案上載到群集中的主資料工作台伺服器。

## 更新IPLookup轉換 {#section-a8b99afe3eb04afabe88e15bd465f935}

1. 在中 [!DNL Profile Manager]，按一下 **[!UICONTROL Dataset]**、 **[!UICONTROL Transformation]**&#x200B;和 **[!UICONTROL Geography]**。

1. 按一下右鍵旁邊的複選標 [!DNL IP Lookup.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。

1. 以滑鼠右鍵按一下新的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 將出現一個轉換配置窗口。

1. 在視窗中，按一下 **[!UICONTROL Transformation]**，然後按一下 **[!UICONTROL Transformations]**。

1. 找到並按一下或 **[!UICONTROL IPLookup Quova]** 之一 **[!UICONTROL IPLookup Digital Envoy]**。

1. 對於「檔案」參數，請更新檔案名稱，以符合Adobe提供之新資料( [!DNL .bin])檔案的名稱。
1. 通過按一下右鍵配置窗口頂部的，然 **[!UICONTROL (modified)]** 後按一下來保存轉換配置檔案 **[!UICONTROL Save]**。

1. 通過按一下右鍵列中旁邊的複選標籤並按一下> [!DNL IP Lookup.cfg] &lt; [!DNL User] > ，將修改的配置檔案保存到使用資料服務的每 **[!UICONTROL Save to]** 個 *配置檔案&#x200B;**[!UICONTROL profile name]***。 資料集描述檔的同步後，開始重新轉換資料。

   如需資料集重新轉換的詳細資訊，請參閱資料集設定指南的「重新處理與 *重新轉換」一章*。

   >[!NOTE]
   >
   >請勿將修改過的設定檔儲存至Adobe提供的任何內部設定檔(包括 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 設定檔)，因為當您安裝這些設定檔的更新時，會覆寫您的變更。

如果您已安裝 [!DNL IP Geo-intelligence] 5.1版 [!DNL IP Geo-location] 或更新版本的and data服務，則您已完成資料服務更新。 但是，如果您安裝了5.1 [!DNL IP Geo-intelligence] 版以 [!DNL IP Geo-location] 前版本的和資料服務，則必須完成以下附加過程。

## 取代查閱檔案 {#section-ced1efa38a76419d812edd35423dbff7}

只有在安裝了5.1版之前的 [!DNL IP Geo-intelligence] and [!DNL IP Geo-location] data服務時，才應完成下列步驟。

1. 在中， [!DNL Server Files Manager]按一下 **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** 或 **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**，然後按一下 **[!UICONTROL Maps]** 以檢視其內容。

1. 在欄中按一 **[!UICONTROL Temp]** 下滑鼠右 **[!UICONTROL Maps]** 鍵，然後按 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*。

1. 將Adobe提供 [!DNL .txt] 的新檔案複製至「地圖」檔案夾視窗。
1. 按一下右鍵檔案列中的複選標籤，然後按一下> [!DNL Temp] &lt; [!DNL .txt] > ，將檔案保存到資料工作台伺服器電腦 **[!UICONTROL Save to]*****[!UICONTROL server name]***。

>[!NOTE]
>
>如果您正在運行群集，請將檔案上載到群集中的主資料工作台伺服器。

## 更新圖層檔案 {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>只有在安裝了5.1版之前的 [!DNL IP Geo-intelligence] and [!DNL IP Geo-location] data服務時，才應完成下列步驟。

針對參照或查閱( [!DNL .layer])檔案的每個圖層( [!DNL IP Geo-intelligence][!DNL IP Geo-location] )檔案，完成這些 [!DNL .txt]步驟。

1. 在資料工作台伺服器安裝目錄的Profiles\*data service name*\Maps資料夾中，在記事本等文字 [!DNL .layer] 編輯器中開啟檔案。

1. 在向 [!DNL Data Paths] 量中，更新查閱檔案的名稱以符合Adobe提供之 [!DNL .txt][!DNL .txt] 新檔案的名稱，如下列檔案範例中反白顯示：

   ```
   Layer = ElementPointLayer:
     Data Paths = vector: 1 items
       0 = Path: Maps\\LookupFileName.txt
     Longitude Column = string: LongitudeColumnName
     Latitude Column = string: LatitudeColumnName
     Name Column = string: LocationColumnName
     Key Column = string: KeyColumnName
     Dimension = ref: wdata/model/dim/DimensionName
     Metric = ref: wdata/model/metric/MetricName
   ```

1. 保存更新的圖層檔案。
1. 對參照或檔案的每 [!DNL .layer] 個檔案重複步 [!DNL IP Geo-intelligence] 驟2 [!DNL IP Geo-location][!DNL .txt] 和3。

