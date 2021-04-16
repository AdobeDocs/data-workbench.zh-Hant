---
description: 地形影像層顯示地球的地形影像。
title: 地形影像層
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
exl-id: 754211a7-0b1f-4353-86f8-9c634d70cd83
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# 地形影像層{#terrain-image-layers}

地形影像層顯示地球的地形影像。

[!DNL Terrain image layers] 會以自訂格 [!DNL Geography] 式儲存在描述檔中。這些影像圖層可由Adobe產生，或Data Workbench伺服器可將使用者提供的地形影像轉換為適合用於全球視覺化的地形圖層。

>[!NOTE]
>
>要使用[!DNL terrain image layers]，必須安裝Adobe提供的[!DNL Terrain Images.cfg]檔案。

要定義地形影像層，您必須具備以下條件：

* **一或多個地形圖** 像檔案，包含要在地球上顯示的影像。
* **一 [!DNL Terrain Images.cfg]** 個檔案，它指定要用於圖層的地形影像檔案。[!DNL Terrain Images.cfg]檔案可讓您新增一或多個來源以建立[!DNL terrain image layer]。 地形影像檔案的格式會決定您應新增的來源類型。 下表說明可用的地形影像層來源，包括支援的地形影像檔案格式：

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
   <td colname="col2"> <p>從24位元無頭RGB檔案建立<span class="wintitle">地形影像圖層</span>，這些檔案經緯度對齊（未投影），其中北為影像頂端，東為右側。 </p> <p>支援的影像格式：RAW </p> <p> <p>注意：此來源需要投影資訊。 有關投影格式的資訊，請參閱<a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e">指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>一般影像，未投影 </p> </td> 
   <td colname="col2"> <p>從24位元、經緯度對齊（未投影）的影像格式建立<span class="wintitle">地形影像圖層</span>，其中北為影像頂端，東為右側。 </p> <p>支援的影像格式：BMP、JPG、PNG、TIFF </p> <p> <p>注意：此來源需要投影資訊。 有關投影格式的資訊，請參閱<a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e">指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>具有嵌入投影的影像 </p> </td> 
   <td colname="col2"> <p>根據將大地測量資料嵌入影像檔案中的影像格式建立<span class="wintitle">地形影像層</span>。 從影像中提取投影資訊。 </p> <p>支援的影像格式：Erdas(IMG)、GeoTIFF </p> <p> <p>注意：此來源通常不需要投影資訊，但支援視需要添加此類資訊。 有關投影格式的資訊，請參閱<a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e">指定地形影像的投影資訊</a>。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**要定義地形影像層**

1. 在Data Workbench中，在&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]**&#x200B;標籤上，按一下&#x200B;**[!UICONTROL Servers Manager]**&#x200B;縮略圖以開啟[!DNL Servers Manager]工作區。
1. 在[!DNL Servers Manager]視窗中，以滑鼠右鍵按一下所要Data Workbench伺服器的圖示，然後按一下&#x200B;**[!UICONTROL Server Files]**。
1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Terrain Images.cfg]伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Terrain Images.cfg]的[!DNL Temp]欄中會出現複選標籤。
1. 在&#x200B;**[!UICONTROL Temp]**&#x200B;欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL Terrain Images.cfg]窗口。
1. 在[!DNL Terrain Images]窗口中，按一下&#x200B;**[!UICONTROL component]**&#x200B;查看其內容。
1. 按一下右鍵&#x200B;**[!UICONTROL Sources]** > **[!UICONTROL Add new]**&#x200B;並選擇以下源類型之一：

   * **[!UICONTROL Raw unprojected bitmap]**。（添加後，此源類型在[!DNL Terrain Images]窗口中被標籤為RawTerrainSource。）

   * **[!UICONTROL General image, unprojected]**。（添加後，此源類型在[!DNL Terrain Images]窗口中標籤為[!DNL GDALTerrainSource]。）

   * **[!UICONTROL Image with embedded projection]**。（添加後，此源類型在[!DNL Terrain Images]窗口中標籤為[!DNL GDALTerrainSource]。）

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
   <td colname="col2"> <p>所有來源皆為選用。 指定要套用至來源影像的Gamma校正。 這可能是可取的，因為Data Workbench通常以高γ設定運行。 預設值為 1。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高度 </p> </td> 
   <td colname="col2"> <p>原始未投影的點陣圖影像需要。 源影像的高度（以像素為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>投影資訊 </p> </td> 
   <td colname="col2"> <p>原始未投影的點陣圖影像和一般影像需要，但是未投影，但支援內嵌投影的影像。 Data Workbench支援地形影像層的經緯度投影和橫向縮放(TM)投影。 預設投影格式是經緯度投影(LatLonProjection)。 </p> <p>有關投影格式的資訊，請參閱<a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e">指定地形影像的投影資訊</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>來源影像 </p> </td> 
   <td colname="col2"> <p>所有來源都需要。 源映像檔案的名稱。 這可以是檔案名或通配符模式。 例如，如果上載了不同日期的相同區域的影像，而關聯的元資料沒有改變，則使用模式可能很有用。 因此，<span class="filepath"> Tysons Corner *.raw</span>等模式會在新增影像時，從<span class="filepath"> Tysons Corner 050211.raw</span>、<span class="filepath"> Tysons Corner 050218.raw</span>建立圖層，如此等，若無需額外設定檔案的參數其他都相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>拼貼壓縮品質 </p> </td> 
   <td colname="col2"> <p>所有來源皆為選用。 對於JPEG壓縮，一個0到100的整數，指定如何平衡影像大小和品質。 （預設值為零。） 數量越高，影像品質越好，但影像越大，Data Workbench的下載時間也越長。 </p> <p> <p>注意： 將影像壓縮至70以下可能會導致影像品質降低。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>瓦片壓縮機 </p> </td> 
   <td colname="col2"> <p>所有來源皆為選用。 指定用什麼壓縮方法來寫入輸出檔案。 目前唯一支援的方法是RAWRGB（預設值，導致無壓縮）和JPEG。 使用JPEG壓縮來減少在描述檔同步期間傳輸的圖層大小。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>寬度 </p> </td> 
   <td colname="col2"> <p>原始未投影的點陣圖影像需要。 源影像的寬度（以像素為單位）。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 使用下表作為參考，編輯源映像位置、臨時映像儲存和寫入層到參數。 這些參數適用於您在此檔案的[!DNL Sources]區段中定義的所有地形影像來源。

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>源映像位置 </p> </td> 
   <td colname="col2"> <p>必填.掃描的目錄，以便將影像轉換為地形圖層。 如果它不是絕對路徑，則相對於Data Workbench伺服器安裝目錄進行解釋。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>臨時映像儲存 </p> </td> 
   <td colname="col2"> <p>選填。用於儲存將源影像轉換為地形圖層時所用臨時檔案的目錄的名稱。 如果它不是絕對路徑，則相對於Data Workbench伺服器安裝目錄進行解釋。 預設位置為<span class="wintitle"> Temp</span>目錄。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將圖層寫入 </p> </td> 
   <td colname="col2"> <p>必填.輸出地形層的目錄。 通常，這是描述檔目錄的Maps子目錄，因此Globe視覺化功能可以找到圖層。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。
1. 要將更新的檔案保存到Data Workbench伺服器電腦，請在[!DNL Server Files Manager]中按一下右鍵[!DNL Temp]列中的[!DNL Terrain Images.cfg]複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]**>*。
