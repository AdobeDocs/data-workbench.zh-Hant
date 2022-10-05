---
description: 如果您訂閱任一資料服務，則必須定期更新Adobe提供的資料服務檔案。
title: 更新資料服務檔案
uuid: 8c14be34-fde3-4c4c-9c22-739863317d6e
exl-id: bb92d40c-cc8d-4ecf-bd48-ed962fd5d73b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 1%

---

# 更新資料服務檔案{#updating-data-service-files}

{{eol}}

如果您訂閱任一資料服務，則必須定期更新Adobe提供的資料服務檔案。

若要這麼做，您必須擁有Data Workbench伺服器上檔案的存取權。

載入 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 資料檔案，您必須完成下列程式。

## 替換資料檔案 {#section-2b53c2951ae04c6fa8b3bdf080469ff6}

1. 在Data Workbench中，於 [!DNL Admin] > [!DNL Dataset and Profile] ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟 [!DNL Servers Manager] 工作區。

1. 在 [!DNL Servers Manager] 視窗中，以滑鼠右鍵按一下您要載入檔案的data workbench伺服器圖示，然後按一下 **[!UICONTROL Server Files]**.

1. 在 [!DNL Server Files Manager]，在 **[!UICONTROL Temp]** 欄 **[!UICONTROL Lookups\IP Geo-location]** 或 **[!UICONTROL Lookups\IP Geo-intelligence]** 按一下 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. 複製 [!DNL .bin] 由Adobe提供到「Lookups\IP Geo-location」或「Lookups\IP Geo-intelligence」資料夾窗口的資料檔案。
1. 以滑鼠右鍵按一下「 」，將檔案儲存至Data Workbench伺服器電腦 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

   如果您執行叢集，請將檔案上傳至叢集中的主資料工作台伺服器。

## 更新IPLookup轉換 {#section-a8b99afe3eb04afabe88e15bd465f935}

1. 在 [!DNL Profile Manager]，按一下 **[!UICONTROL Dataset]**, **[!UICONTROL Transformation]**，和 **[!UICONTROL Geography]**.

1. 以滑鼠右鍵按一下旁的核取記號 [!DNL IP Lookup.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。

1. 按一下右鍵新複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 將顯示轉換配置窗口。

1. 在視窗中，按一下 **[!UICONTROL Transformation]**，然後按一下 **[!UICONTROL Transformations]**.

1. 找到並按一下 **[!UICONTROL IPLookup Quova]** 或 **[!UICONTROL IPLookup Digital Envoy]**.

1. 對於File參數，更新檔案的名稱以符合新資料的名稱( [!DNL .bin])由Adobe提供的檔案。
1. 按一下右鍵以儲存轉換組態檔 **[!UICONTROL (modified)]** ，然後按一下 **[!UICONTROL Save]**.

1. 以滑鼠右鍵按一下旁的核取標籤，將修改的設定檔儲存至使用資料服務的每個設定檔 [!DNL IP Lookup.cfg] 在 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*. 同步資料集設定檔後，即會開始重新轉換資料。

   如需資料集重新轉換的相關資訊，請參閱 *資料集組態指南*.

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔(包括 [!DNL IP Geo-location] 或 [!DNL IP Geo-intelligence] 設定檔)，當您安裝這些設定檔的更新時，變更會遭到覆寫。

若您已安裝 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 5.1版或更新版本的資料服務，您已完成資料服務更新。 不過，若您已安裝 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 資料服務5.1版之前，您必須完成下列其他程式。

## 取代查閱檔案 {#section-ced1efa38a76419d812edd35423dbff7}

只有在安裝 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 5.1版之前的資料服務。

1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-intelligence]** 或 **[!UICONTROL Profiles]** > **[!UICONTROL IP Geo-location]**，然後按一下 **[!UICONTROL Maps]** 來檢視其內容。

1. 在 **[!UICONTROL Temp]** 欄 **[!UICONTROL Maps]** 按一下 **[!UICONTROL Open]** > *&lt;**[!UICONTROL folder]**>*.

1. 複製新 [!DNL .txt] 由Adobe提供的檔案。
1. 以滑鼠右鍵按一下 [!DNL Temp] 欄 [!DNL .txt] 檔案，按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>如果您執行叢集，請將檔案上傳至叢集中的主資料工作台伺服器。

## 更新層檔案 {#section-8b84e7099bad40c9a69665a4890fe66e}

>[!NOTE]
>
>只有在安裝 [!DNL IP Geo-intelligence] 和 [!DNL IP Geo-location] 5.1版之前的資料服務。

針對每個層完成這些步驟( [!DNL .layer])檔案 [!DNL IP Geo-intelligence] 或 [!DNL IP Geo-location] 查閱( [!DNL .txt])檔案。

1. 在Data Workbench伺服器安裝目錄內的Profiles\*data service name*\Maps資料夾中，開啟 [!DNL .layer] 檔案（如記事本）。

1. 在 [!DNL Data Paths] 向量，更新 [!DNL .txt] 查閱檔案以符合新 [!DNL .txt] 由Adobe提供的檔案，如下列檔案範例中強調顯示：

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

1. 保存更新的層檔案。
1. 對每個 [!DNL .layer] 引用的檔案 [!DNL IP Geo-intelligence] 或 [!DNL IP Geo-location] [!DNL .txt] 檔案。
