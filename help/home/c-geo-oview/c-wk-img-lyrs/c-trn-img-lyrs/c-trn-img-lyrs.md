---
description: 在資料工作台中，地形影像層顯示地球的地形影像。
solution: Analytics
title: 使用地形圖層
topic: Data workbench
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# 使用地形圖層{#working-with-terrain-image-layers}

在資料工作台中，地形影像層顯示地球的地形影像。

地形影像圖層會以自訂 [!DNL Geography] 格式儲存在描述檔中。 這些影像圖層可由Adobe產生，或資料工作台伺服器可將使用者提供的地形影像轉換為適合用於全球視覺化的地形圖層。

>[!NOTE]
>
>若要使用地形影像圖層，您必須安裝Adobe [!DNL Terrain Images.cfg] 提供的檔案。 如需安裝指示，請參 [閱安裝資料工作台地理](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)。

要定義地形影像層，您必須具備以下條件：

* **一個或多個地形影像檔案** ，包含要在地球上顯示的影像。
* **Terrain Images.cfg** 檔案，指定要用於圖層的地形影像檔。 此 [!DNL Terrain Images.cfg] 檔案可讓您新增一或多個來源，以建立地形影像圖層。 地形影像檔案的格式會決定您應新增的來源類型。 下表說明可用的地形影像層來源，包括支援的地形影像檔案格式：

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
   <td colname="col2"> <p>從24位元無頭RGB檔案建立地形影像圖層，這些檔案經緯度對齊（未投影），其中北為影像的頂端，東為右側。 </p> <p>支援的影像格式：RAW </p> <p> <p>注意：此來源需要投影資訊。 有關投影格式的資訊，請參 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 閱指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一般影像，未投影 </td> 
   <td colname="col2"> <p>從24位元、經緯度對齊（未投影）的影像格式建立地形影像圖層，其中北為影像頂端，東為右側。 </p> <p>支援的影像格式：BMP、JPG、PNG、TIFF </p> <p> <p>注意：此來源需要投影資訊。 有關投影格式的資訊，請參 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 閱指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 具有嵌入投影的影像 </td> 
   <td colname="col2"> <p>從影像格式建立地形影像圖層，將大地測量資料內嵌在影像檔中。 從影像中提取投影資訊。 </p> <p>支援的影像格式：Erdas(IMG)、GeoTIFF </p> <p> <p>注意：此來源通常不需要投影資訊，但支援視需要添加此類資訊。 有關投影格式的資訊，請參 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 閱指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**要定義地形影像層**

1. 在資料工作台的「 >」標 [!DNL Admin] 簽 [!DNL Dataset and Profile] 上，按一下縮 **[!UICONTROL Servers Manager]** 圖以開啟工作 [!DNL Servers Manager] 區。

1. 在視窗 [!DNL Servers Manager] 中，以滑鼠右鍵按一下所需資料工作台伺服器的圖示，然後按一下 **[!UICONTROL Server Files]**。

1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Components]** 查看其內容。 文 [!DNL Terrain Images.cfg] 件位於此目錄中。

1. 按一下右鍵的伺服器名列中的複選標籤， [!DNL Terrain Images.cfg]然後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在 [!DNL Temp] 的欄中 [!DNL Terrain Images.cfg.]

1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 出現 [!DNL Terrain Images.cfg]窗口。

1. 在視窗 [!DNL Terrain Images] 中，按一 **[!UICONTROL component]** 下以檢視其內容。

1. 按一下右鍵 **[!UICONTROL Sources]** >並 **[!UICONTROL Add new]** 選擇以下源類型之一：

   * **[!UICONTROL Raw unprojected bitmap]**。(新增後，此來源類型會在視窗中標示為RawTerrainSource [!DNL Terrain Images] 。)

   * **[!UICONTROL General image, unprojected]**。(添加後，該源類型在窗口中標籤為GDALTerrainSource [!DNL Terrain Images] 。)

   * **[!UICONTROL Image with embedded projection]**。(添加後，該源類型在窗口中標籤為GDALTerrainSource [!DNL Terrain Images] 。)

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
   <td colname="col2"> 所有來源皆為選用。 指定要套用至來源影像的Gamma校正。 這可能是可取的，因為資料工作台通常以高Gamma設定執行。 預設值為 1。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 高度 </td> 
   <td colname="col2"> 原始未投影的點陣圖影像需要。 源影像的高度（以像素為單位）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 投影資訊 </td> 
   <td colname="col2"> <p>原始未投影的點陣圖影像和一般影像需要，但是未投影，但支援內嵌投影的影像。 資料工作台<span class="wintitle"> Geography</span> 支援地形影像層的經緯度投影和橫向縮圖(TM)投影。 預設投影格式是經緯度投影(LatLonProjection)。 </p> <p>有關投影格式的資訊，請參 <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> 閱指定地形影像的投影資訊</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 來源影像 </td> 
   <td colname="col2">所有來源都需要。 源映像檔案的名稱。 這可以是檔案名或通配符模式。 例如，如果上載了不同日期的相同區域的影像，而關聯的元資料沒有改變，則使用模式可能很有用。 因此，當新增影像時，像「<span class="filepath"> Tysons Corner *.raw</span>」這樣的圖樣會從 <span class="filepath"> Tysons Corner 050211.raw</span>、 <span class="filepath"></span>Tysons Corner 050218.raw等建立圖層，若檔案參數不相同，則不需額外設定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 拼貼壓縮品質 </td> 
   <td colname="col2"> <p>所有來源皆為選用。 對於JPEG壓縮，一個0到100的整數，指定如何平衡影像大小和品質。 （預設值為零。）數量越高，影像品質越好，但為資料工作台使用者產生的影像越大，下載時間也越長。 </p> <p>將影像壓縮至70以下可能會導致影像品質降低。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 瓦片壓縮機 </td> 
   <td colname="col2"> 所有來源皆為選用。 指定用什麼壓縮方法來寫入輸出檔案。 目前唯一支援的方法是RAWRGB（預設值，導致無壓縮）和JPEG。 使用JPEG壓縮來減少在描述檔同步期間傳輸的圖層大小。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寬度 </td> 
   <td colname="col2"> 原始未投影的點陣圖影像需要。 源影像的寬度（以像素為單位）。 </td> 
  </tr> 
 </tbody> 
</table>

1. 使用下表作為參考，編輯源映像位置、臨時映像儲存和寫入層到參數。 這些參數適用於您在此檔案的「來源」區段中定義的所有地形影像來源。

   | 參數 | 說明 |
   |---|---|
   | 源映像位置 | 必填.掃描的目錄，以便將影像轉換為地形圖層。 如果它不是絕對路徑，則會相對於資料工作台伺服器安裝目錄進行解釋。 |
   | 臨時映像儲存 | 選填。用於儲存將源影像轉換為地形圖層時所用臨時檔案的目錄的名稱。 如果它不是絕對路徑，則會相對於資料工作台伺服器安裝目錄進行解釋。 預設位置是Temp目錄。 |
   | 將圖層寫入 | 必填.輸出地形層的目錄。 通常，這是描述檔目錄的Maps子目錄，以便視覺 [!DNL Globe] 化能夠找到圖層。 |

1. 以滑鼠右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。

1. 若要將更新的檔案儲存至資料工作台伺服器機器，請 [!DNL Server Files Manager]在欄中以滑鼠右鍵按一下 [!DNL Terrain Images.cfg] 的 [!DNL Temp] 核取標籤，然後按 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

