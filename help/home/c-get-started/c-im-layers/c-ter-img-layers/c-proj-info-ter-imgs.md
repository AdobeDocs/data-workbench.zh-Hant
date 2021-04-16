---
description: 資料工作台支援所有地形影像層來源的經緯度投影和通用橫向縮放(UTM)投影。
title: 指定地形影像的投影資訊
uuid: cc1e1e35-6b23-4121-a9f5-489001cb2ef8
exl-id: 2638c5d4-164d-411b-8464-0a3af81b6537
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 3%

---

# 指定地形影像的投影資訊{#specify-projection-information-for-terrain-images}

資料工作台支援所有地形影像層來源的經緯度投影和通用橫向縮放(UTM)投影。

原始的未投影點陣圖和一般影像（未投影）需要投影資訊。 您可以為具有嵌入投影資訊的影像指定投影資訊，但通常不需要該資訊，因為投影的參數是由嵌入影像本身的大地測量資料自動確定的。 以下各節提供有關在[!DNL Terrain Images.cfg]檔案中指定這些投影格式的詳細資訊。

## 經緯度投影 {#section-6e335357ec28462ba39c565e0a5986c7}

[!DNL Terrain Images.cfg]檔案中的經緯度投影格式(LatLonProjection)由經緯度的四個參數定義。

要為未投影的影像（原始未投影的點陣圖和常規影像，未投影的影像）指定LatLonProjection，可以在Data Workbench的[!DNL Terrain Images.cfg]窗口中輸入LatLonProjection的設定。

要為具有嵌入投影資訊的影像指定LatLonProjection，必須在記事本等文本編輯器中開啟[!DNL Terrain Images.cfg]檔案，將「投影資訊」參數設定為LatLonProjection，並添加[!DNL LatLonProjection]的設定。

**為未投影的影像指定LatLonProjection**

1. 在Data Workbench中開啟[!DNL Terrain Images.cfg]檔案並添加地形影像層源，如[要定義地形影像層](../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-ter-img-layers.md#concept-f4b3a20969354ca38955e3fd5beb0f4f)中所述。
1. 使用下列參數表作為參考線編輯「投影資訊」參數：

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
   <td colname="col2"> <p>影像上緣的緯度，以度為單位，90是北極，-90是南極。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lat1 </p> </td> 
   <td colname="col2"> <p>影像底部邊緣的緯度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon0 </p> </td> 
   <td colname="col2"> <p>影像左邊緣的經度，以度為單位，正數為東，負數為西經。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Lon1 </p> </td> 
   <td colname="col2"> <p>影像右側邊緣的經度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。
1. 要將本地更改保存到Data Workbench伺服器電腦，請在[!DNL Server Files Manager]中按一下右鍵[!DNL Temp]列中的[!DNL Terrain Images.cfg]複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]***。

**為嵌入的投影資訊中的影像指定LatLonProjection**

在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。

按一下右鍵[!DNL Terrain Images.cfg]伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Terrain Images.cfg]的[!DNL Temp]欄中會出現複選標籤。

在[!DNL Temp]欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 [!DNL Terrain Images.cfg]檔案將出現在記事本窗口中。

使用以下示例檔案片段作為參考，編輯「投影資訊」參數。 請務必指定如下突出顯示的投影類型。 有關參數的說明，請參見上一步中的「LatLonProjection參數」表。

```
Projection Info = LatLonProjection:
  Lat0 = double: 90
  Lat1 = double: -90
  Lon0 = double: -180
  Lon1 = double: 180
```

## 世界橫麥卡托投影 {#section-606df0ed1c2d4a6bac3ff0fa2cfb3e82}

通用橫向縮放器(UTM)投影由8個參數定義。 為地形影像層指定「通用橫向縮放器」投影時，您的地形影像檔案必須與朝影像頂部向北的假（投影）和向影像右側的假（投影）對齊。

要為任何地形影像源指定UTM投影，必須在文本編輯器（如記事本）中開啟[!DNL Terrain Images.cfg]檔案，將「投影資訊」參數設定為「TransverseMercatorProjection」，並添加UTM投影的設定。

**要指定通用橫向縮放器投影**

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。
1. 按一下右鍵[!DNL Terrain Images.cfg]伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Terrain Images.cfg.]的[!DNL Temp]欄中會出現複選標籤
1. 在[!DNL Temp]欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 [!DNL Terrain Images.cfg]檔案將出現在記事本窗口中。
1. 使用下列示例檔案片段和參數表作為參考線編輯「投影資訊」參數。 請務必指定如下突出顯示的投影類型。

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
   <td colname="col1"> <p>橢球反平面化橢球半長軸 </p> </td> 
   <td colname="col2"> <p>用於投影的橢球參數。 半長軸以米為單位指定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>誤報 </p> </td> 
   <td colname="col2"> <p>投影中心子午的假鑄，以米為單位。 對於UTM，這總是50萬。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False Northing </p> </td> 
   <td colname="col2"> <p>赤道的假北方在投影中，以米為單位。 對於UTM，北半球區域為0，南半球區域為10,000。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>西北角坐標，東南角坐標 </p> </td> 
   <td colname="col2"> <p>影像左上角和右下角的座標（以投影米數表示）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prime Meridian </p> </td> 
   <td colname="col2"> <p>投影中心子午線的經度，以格林威治以東的度數指定。 負數可用來指定西向度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>比例因子 </p> </td> 
   <td colname="col2"> <p>投影柱的半徑與橢球的半長軸之比。 對於通用橫向縮放器(UTM)投影，此值一律為0.9996。 </p> </td> 
  </tr> 
 </tbody> 
</table>
