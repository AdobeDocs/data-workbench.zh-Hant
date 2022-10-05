---
description: Data Workbench支援經緯度投影和通用橫麥卡托(UTM)投影，適用於所有地形影像層來源。
title: 指定地形影像的投影資訊
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# 指定地形影像的投影資訊{#specify-projection-information-for-terrain-images}

{{eol}}

Data Workbench支援經緯度投影和通用橫麥卡托(UTM)投影，適用於所有地形影像層來源。

原始未投影點陣圖和未投影的一般影像需要投影資訊。 可以指定具有嵌入投影資訊的影像的投影資訊，但通常不需要，因為投影的參數是由嵌入影像本身的大地資料自動確定的。 以下各節提供有關在 [!DNL Terrain Images.cfg] 檔案。

## 經緯度投影 {#section-6e335357ec28462ba39c565e0a5986c7}

以下欄位中的經緯度投影格式(LatLonProjection): [!DNL Terrain Images.cfg] 檔案由經緯度的四個參數定義。

要為未投影的影像（原始未投影點陣圖和常規影像，未投影）指定LatLonProjection，可在 [!DNL Terrain Images.cfg] 視窗Data Workbench。

要為包含嵌入投影資訊的影像指定LatLonProjection，必須開啟 [!DNL Terrain Images.cfg] 在文本編輯器（如記事本）中，將「投影資訊」參數設定為LatLonProjection，並為添加設定 [!DNL LatLonProjection].

**為未投影的影像指定LatLonProjection**

1. 開啟 [!DNL Terrain Images.cfg] 檔案Data Workbench，並新增地形影像層來源，如 [定義地形影像層](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f).
1. 使用下列參數表作為指南編輯「投影資訊」參數：

<table id="table_32F6EADB2DA34592ABD6FFAC9E00BB27"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Lat0 </p> </td> 
   <td colname="col2"> <p>影像上邊緣的緯度，以度為單位，其中90是北極，-90是南極。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>影像底邊的緯度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>影像左邊的經度，以度為單位，正數為東，負數為西經。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>影像右側邊緣的經度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下滑鼠右鍵以儲存檔案 **[!UICONTROL (modified)]** 按一下 **[!UICONTROL Save]**.
1. 若要將本機所做的變更儲存至Data Workbench伺服器電腦，請在 [!DNL Server Files Manager]，按一下右鍵的複選標籤 [!DNL Terrain Images.cfg] 在 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

**為嵌入的投影資訊內的影像指定LatLonProjection**

在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Terrain Images.cfg] 檔案位於此目錄中。

按一下右鍵伺服器名稱列中的複選標籤， [!DNL Terrain Images.cfg]，然後按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Terrain Images.cfg].

在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 此 [!DNL Terrain Images.cfg] 檔案將出現在記事本窗口中。

使用以下示例檔案片段作為指南編輯「投影資訊」參數。 請務必指定投影類型，如下面突出顯示。 有關參數的說明，請參閱上一步過程中的LatLonProjection參數表。

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## 世界橫麥卡托投影 {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

通用橫麥卡托(UTM)投影由8個參數定義。 為地形影像層指定通用橫麥卡托投影時，您的地形影像檔案必須與朝影像頂端的偽（投影）對齊，並且與影像右側的偽東對齊。

要為任何地形影像源指定UTM投影，必須開啟 [!DNL Terrain Images.cfg] 在文本編輯器（如記事本）中，將「投影資訊」參數設定為「VersouseMercatorProjection」，並添加UTM投影的設定。

**指定通用橫麥卡托投影**

1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Terrain Images.cfg] 檔案位於此目錄中。
1. 按一下右鍵伺服器名稱列中的複選標籤， [!DNL Terrain Images.cfg]，然後按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Terrain Images.cfg.]
1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 此 [!DNL Terrain Images.cfg] 檔案將出現在記事本窗口中。
1. 使用以下示例檔案片段和參數表作為參考線編輯「投影資訊」參數。 請務必指定投影類型，如下面突出顯示。

   ```
   Projection Info = TransverseMercatorProjection:
     Ellipsoid Inverse Flattening = double: 294.9786982139006
     Ellipsoid Semimajor Axis = double: 6378206.4000000004
     False Easting = double: 500000
     False Northing = double: 0
     Northwest Corner Coordinates = v3d: (550339, 5.42059e+006, 0)
     Prime Meridian = double: -123
     Scale Factor = double: 0.9996
     Southeast Corner Coordinates = v3d: (555099, 5.41356e+006, 0)
   ```

<table id="table_71AEEAE808B9436B9846987A54D5D1D2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>橢球反扁平化、橢球半長軸 </p> </td> 
   <td colname="col2"> <p>用於投影的橢球的參數。 半長軸以公尺為單位指定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>誤判 </p> </td> 
   <td colname="col2"> <p>投影中心子午的假報，以公尺為單位。 對於UTM，這一直是50萬。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>偽標準 </p> </td> 
   <td colname="col2"> <p>赤道的偽北線，以公尺為單位。 對於UTM，北半球區為0，南半球區為10,000。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>西北角坐標，東南角坐標 </p> </td> 
   <td colname="col2"> <p>影像左上角和右下角的座標（以投影的公尺為單位）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>主子午線 </p> </td> 
   <td colname="col2"> <p>投影中心子午線的經度，以格林尼治以東度指定。 負數可用於指定西度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>比例因子 </p> </td> 
   <td colname="col2"> <p>投影圓柱半徑與橢球的半長軸的比。 對於Universal Versal Mercator(UTM)投影，這始終為0.9996。 </p> </td> 
  </tr> 
 </tbody> 
</table>
