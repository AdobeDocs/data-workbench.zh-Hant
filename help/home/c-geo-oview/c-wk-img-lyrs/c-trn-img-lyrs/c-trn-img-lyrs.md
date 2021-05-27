---
description: 在Data Workbench中，地形影像層會顯示地球的地形影像。
title: 使用地形影像層
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# 使用地形影像層{#working-with-terrain-image-layers}

在Data Workbench中，地形影像層會顯示地球的地形影像。

地形影像層以自訂格式儲存在[!DNL Geography]設定檔中。 這些影像層可由Adobe產生，或Data Workbench伺服器可將使用者提供的地形影像轉換為適合用於全球視覺效果的地形層。

>[!NOTE]
>
>要使用地形影像層，必須安裝由Adobe提供的[!DNL Terrain Images.cfg]檔案。 有關安裝說明，請參閱[安裝Data WorkbenchGeography](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)。

若要定義地形影像層，您必須具備下列條件：

* **一個或多個地形影** 像檔案，包含要在地球上顯示的影像。
* **指定用於圖** 層的地形影像檔案的地形影像.cfgfile。[!DNL Terrain Images.cfg]檔案可讓您新增一或多個來源以建立地形影像層。 地形影像檔案的格式決定您應新增的來源類型。 下表提供可用地形影像層來源的說明，包括支援的地形影像檔案格式：

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 原始未投影點陣圖 </td> 
   <td colname="col2"> <p>從經緯度對齊（未投影）的24位無頭RGB檔案建立地形影像層，其中北是影像的頂部，東是右側。 </p> <p>支援的影像格式：原始 </p> <p> <p>注意：此源需要投影資訊。 有關投影格式的資訊，請參閱<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一般影像，未投影 </td> 
   <td colname="col2"> <p>以24位經緯度對齊（未投影）的影像格式建立地形影像層，其中北部是影像的頂部，而東部是右側。 </p> <p>支援的影像格式：BMP、JPG、PNG、TIFF </p> <p> <p>注意：此源需要投影資訊。 有關投影格式的資訊，請參閱<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有嵌入投影的影像 </td> 
   <td colname="col2"> <p>從將大地資料嵌入影像檔案中的影像格式建立地形影像層。 從影像中提取投影資訊。 </p> <p>支援的影像格式：Erdas(IMG)、 GeoTIFF </p> <p> <p>注意：此源通常不需要投影資訊，但支援在需要時添加這些資訊。 有關投影格式的資訊，請參閱<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**定義地形影像層**

1. 在Data Workbench中，在[!DNL Admin] > [!DNL Dataset and Profile]標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮圖以開啟[!DNL Servers Manager]工作區。

1. 在[!DNL Servers Manager]視窗中，以滑鼠右鍵按一下所需Data Workbench伺服器的圖示，然後按一下&#x200B;**[!UICONTROL Server Files]**。

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Terrain Images.cfg]的伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Terrain Images.cfg.]的[!DNL Temp]列中出現複選標籤

1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 將顯示[!DNL Terrain Images.cfg]窗口。

1. 在[!DNL Terrain Images]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。

1. 按一下右鍵&#x200B;**[!UICONTROL Sources]** > **[!UICONTROL Add new]**&#x200B;並選擇以下源類型之一：

   * **[!UICONTROL Raw unprojected bitmap]**。（添加後，此源類型在[!DNL Terrain Images]窗口中被標籤為RawTerrainSource。）

   * **[!UICONTROL General image, unprojected]**。（添加後，此源類型在[!DNL Terrain Images]窗口中被標籤為GDALTerrainSource。）

   * **[!UICONTROL Image with embedded projection]**。（添加後，此源類型在[!DNL Terrain Images]窗口中被標籤為GDALTerrainSource。）

1. 使用以下示例檔案和參數表作為參考線，根據需要編輯源的參數。

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> 所有來源均可選。 指定要應用於源影像的伽馬校正。 這可能是理想的作法，因為Data Workbench通常會以高Gamma設定執行。 預設值為 1。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 高度 </td> 
   <td colname="col2"> 原始未投影點陣圖影像需要。 源影像的高度（像素）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 投影資訊 </td> 
   <td colname="col2"> <p>原始未投影點陣圖影像和一般影像需要，未投影，但支援嵌入投影的影像。 Data Workbench<span class="wintitle"> Geography</span>支援地形影像層的經緯度投影和橫麥卡托(TM)投影。 預設投影格式為經緯度投影(LatLonProjection)。 </p> <p>有關投影格式的資訊，請參閱<a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd">指定地形影像的投影資訊</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 源影像 </td> 
   <td colname="col2">所有源均必需。 源映像檔案的名稱。 這可以是檔案名或通配符模式。 例如，如果上傳了不同日期的相同區域的影像，且相關中繼資料沒有變更，則使用模式可能會很有用。 因此，當添加新影像時，「<span class="filepath"> Tysons Corner *.raw</span>」這樣的模式將從<span class="filepath"> Tysons Corner 050211.raw</span>、<span class="filepath"> Tysons Corner 050218.raw</span>等中建立圖層，如果檔案的參數不相同，則無需額外配置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 磁貼壓縮質量 </td> 
   <td colname="col2"> <p>所有來源均可選。 對於JPEG壓縮，一個0到100的整數，指定如何平衡影像大小和質量。 （預設值為零。） 數字越高，影像品質越好，但Data Workbench使用者的影像越大，下載時間也越長。 </p> <p>壓縮到70以下的影像可能導致影像退化。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 瓦塊壓縮機 </td> 
   <td colname="col2"> 所有來源均可選。 指定用於寫入輸出檔案的壓縮方法。 目前唯一支援的方法是RAWRGB（預設值，導致無壓縮）和JPEG。 使用JPEG壓縮來減小在輪廓同步期間傳輸的層的大小。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寬度 </td> 
   <td colname="col2"> 原始未投影點陣圖影像需要。 源影像的寬度（像素）。 </td> 
  </tr> 
 </tbody> 
</table>

1. 使用下表作為指南，編輯源映像位置、臨時映像儲存和寫入層到參數。 這些參數適用於您在此檔案的「源」部分中定義的所有地形影像源。

   | 參數 | 說明 |
   |---|---|
   | 源影像位置 | 必填。掃描的目錄，以便影像轉換為地形層。 如果它不是絕對路徑，則會相對於Data Workbench伺服器安裝目錄進行解譯。 |
   | 臨時映像儲存 | 選填。用於儲存將源映像轉換為地形層時所用的臨時檔案的目錄的名稱。 如果它不是絕對路徑，則會相對於Data Workbench伺服器安裝目錄進行解譯。 預設位置為Temp目錄。 |
   | 將圖層寫入 | 必填。輸出地形層的目錄。 通常，這是配置檔案目錄的Maps子目錄，以便[!DNL Globe]視覺效果可以找到層。 |

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。

1. 若要將更新的檔案儲存至Data Workbench伺服器電腦，請在[!DNL Server Files Manager]中，以滑鼠右鍵按一下[!DNL Temp]欄中的[!DNL Terrain Images.cfg]勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***。
