---
description: 地形影像層顯示地球的地形影像。
title: 地形影像層
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
exl-id: 754211a7-0b1f-4353-86f8-9c634d70cd83
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# 地形影像層{#terrain-image-layers}

{{eol}}

地形影像層顯示地球的地形影像。

[!DNL Terrain image layers] 儲存於 [!DNL Geography] 設定檔。 這些影像層可由Adobe產生，或Data Workbench伺服器可將使用者提供的地形影像轉換為適合用於全球視覺效果的地形層。

>[!NOTE]
>
>使用 [!DNL terrain image layers]，您必須安裝 [!DNL Terrain Images.cfg] 檔案(由Adobe提供)。

若要定義地形影像層，您必須具備下列條件：

* **一個或多個地形影像檔案** 包含要在地球上顯示的影像。
* **A [!DNL Terrain Images.cfg] 檔案** 這指定要用於圖層的地形影像檔案。 此 [!DNL Terrain Images.cfg] 檔案可讓您新增一或多個來源以建立 [!DNL terrain image layer]. 地形影像檔案的格式決定您應新增的來源類型。 下表提供可用地形影像層來源的說明，包括支援的地形影像檔案格式：

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>原始未投影點陣圖 </p> </td> 
   <td colname="col2"> <p>建立 <span class="wintitle"> 地形影像層</span> 來自經緯度對齊（未投影）的24位無頭RGB檔案，其中，北是影像的頂部，東是右側。 </p> <p>支援的影像格式：原始 </p> <p> <p>注意：此源需要投影資訊。 有關投影格式的資訊，請參見 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 指定地形影像的投影資訊</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>一般影像，未投影 </p> </td> 
   <td colname="col2"> <p>建立 <span class="wintitle"> 地形影像層</span> 從24位經緯度對齊（未投影）影像格式，其中北是影像的頂端，東是右側。 </p> <p>支援的影像格式：BMP,JPG, PNG,TIFF </p> <p> <p>注意：此源需要投影資訊。 有關投影格式的資訊，請參見 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 指定地形影像的投影資訊</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>具有嵌入投影的影像 </p> </td> 
   <td colname="col2"> <p>建立 <span class="wintitle"> 地形影像層</span> 從將大地測量資料嵌入影像檔案的影像格式。 從影像中提取投影資訊。 </p> <p>支援的影像格式：Erdas(IMG)、 GeoTIFF </p> <p> <p>注意：此源通常不需要投影資訊，但支援在需要時添加這些資訊。 有關投影格式的資訊，請參見 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 指定地形影像的投影資訊</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**定義地形影像層**

1. 在Data Workbench中，在 **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** ，按一下 **[!UICONTROL Servers Manager]** 縮圖以開啟 [!DNL Servers Manager] 工作區。
1. 在 [!DNL Servers Manager] 窗口，按一下右鍵所需Data Workbench伺服器的表徵圖，然後按一下 **[!UICONTROL Server Files]**.
1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Terrain Images.cfg] 檔案位於此目錄中。
1. 按一下右鍵伺服器名稱列中的複選標籤， [!DNL Terrain Images.cfg]，然後按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Terrain Images.cfg].
1. 在 **[!UICONTROL Temp]** 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 此 [!DNL Terrain Images.cfg] 的上界。
1. 在 [!DNL Terrain Images] 按一下 **[!UICONTROL component]** 來檢視其內容。
1. 按一下右鍵 **[!UICONTROL Sources]** > **[!UICONTROL Add new]** 並選擇以下源類型之一：

   * **[!UICONTROL Raw unprojected bitmap]**。(新增後，此來源類型在 [!DNL Terrain Images] 窗口。)

   * **[!UICONTROL General image, unprojected]**。(新增後，此來源類型就會加上標籤 [!DNL GDALTerrainSource] 在 [!DNL Terrain Images] 窗口。)

   * **[!UICONTROL Image with embedded projection]**。(新增後，此來源類型就會加上標籤 [!DNL GDALTerrainSource] 在 [!DNL Terrain Images] 窗口。)

1. 使用以下示例檔案和參數表作為參考線，根據需要編輯源的參數。

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> <p>所有來源均可選。 指定要應用於源影像的伽馬校正。 這可能是理想的，因為Data Workbench通常以高伽馬設定運行。 預設值為 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高度 </p> </td> 
   <td colname="col2"> <p>原始未投影點陣圖影像需要。 源影像的高度（像素）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>投影資訊 </p> </td> 
   <td colname="col2"> <p>原始未投影點陣圖影像和一般影像需要，未投影，但支援嵌入投影的影像。 Data Workbench支援地形影像層的經緯度投影和橫麥卡托(TM)投影。 預設投影格式為經緯度投影(LatLonProjection)。 </p> <p>有關投影格式的資訊，請參見 <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> 指定地形影像的投影資訊</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>源影像 </p> </td> 
   <td colname="col2"> <p>所有源均必需。 源映像檔案的名稱。 這可以是檔案名或通配符模式。 例如，如果上傳了不同日期的相同區域的影像，且相關中繼資料沒有變更，則使用模式可能會很有用。 因此，模式類似 <span class="filepath"> 泰森斯角*.raw</span> 建立層 <span class="filepath"> 泰森斯角050211.raw</span>, <span class="filepath"> 泰森斯角050218.raw</span>，以此類推，如果檔案的參數相同，則無需額外設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>磁貼壓縮質量 </p> </td> 
   <td colname="col2"> <p>所有來源均可選。 對於JPEG壓縮，一個0到100的整數，指定如何平衡影像大小和質量。 （預設值為零。） 數字越高，影像品質越好，但影像越大，Data Workbench使用者的下載時間也越長。 </p> <p> <p>注意：壓縮到70以下的影像可能導致影像退化。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>瓦塊壓縮機 </p> </td> 
   <td colname="col2"> <p>所有來源均可選。 指定用於寫入輸出檔案的壓縮方法。 目前唯一支援的方法是RAWRGB（預設值，導致無壓縮）和JPEG。 使用JPEG壓縮來縮小配置檔案同步期間傳輸的層的大小。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>寬度 </p> </td> 
   <td colname="col2"> <p>原始未投影點陣圖影像需要。 源影像的寬度（像素）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 使用下表作為指南，編輯源映像位置、臨時映像儲存和寫入層到參數。 這些參數適用於您在 [!DNL Sources] 區段。

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>源影像位置 </p> </td> 
   <td colname="col2"> <p>必填。掃描的目錄，以便影像轉換為地形層。 如果它不是絕對路徑，則會相對於Data Workbench伺服器安裝目錄進行解釋。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>臨時映像儲存 </p> </td> 
   <td colname="col2"> <p>選填。用於儲存將源映像轉換為地形層時所用的臨時檔案的目錄的名稱。 如果它不是絕對路徑，則會相對於Data Workbench伺服器安裝目錄進行解釋。 預設位置為 <span class="wintitle"> 臨時</span> 目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將圖層寫入 </p> </td> 
   <td colname="col2"> <p>必填。輸出地形層的目錄。 通常，這是配置檔案目錄的「地圖」子目錄，因此「全球」視覺效果可以查找層。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下滑鼠右鍵以儲存檔案 **[!UICONTROL (modified)]** 按一下 **[!UICONTROL Save]**.
1. 若要將更新的檔案儲存至Data Workbench伺服器電腦，請在 [!DNL Server Files Manager]，按一下右鍵的複選標籤 [!DNL Terrain Images.cfg] 在 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
