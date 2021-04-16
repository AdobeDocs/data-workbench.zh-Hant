---
description: 地形影像。cfg檔案中的經緯度投影格式(LatLonProjection)由經緯度的四個參數定義。
title: 經緯度投影
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# 經緯度投影{#latitude-longitude-projections}

地形影像。cfg檔案中的經緯度投影格式(LatLonProjection)由經緯度的四個參數定義。

若要為未投影的影像（原始未投影的點陣圖和一般影像，未投影）指定LatLonProjection，您可以在資料工作台的[!DNL Terrain Images.cfg]視窗中輸入LatLonProjection的設定。 請參閱[為未投影的影像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)。

要為具有嵌入投影資訊的影像指定LatLonProjection，必須在記事本等文本編輯器中開啟[!DNL Terrain Images.cfg]檔案，將投影資訊參數設定為&quot;LatLonProjection&quot;，並添加LatLonProjection的設定。 請參閱[要為嵌入的投影資訊中的影像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)。

* [為未投影的影像指定LatLon投影](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [要為嵌入的投影資訊中的影像指定LatLon投影……](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 為未投影的影像指定LatLonProjection {#section-26554eefe645481faba68396fa13756a}

1. 在資料工作台中開啟[!DNL Terrain Images.cfg]檔案，並新增地形影像圖層來源，如[要定義地形影像圖層](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)所述。

1. 使用下列參數表作為參考線編輯「投影資訊」參數：

   | 參數 | 說明 |
   |---|---|
   | Lat0 | 影像上緣的緯度，以度為單位，90是北極，-90是南極。 |
   | Lat1 | 影像底部邊緣的緯度。 |
   | Lon0 | 影像左邊緣的經度，以度為單位，正數為東，負數為西經。 |
   | Lon1 | 影像右側邊緣的經度。 |

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。

1. 若要將本機所做的變更儲存至資料工作台伺服器機器，請在[!DNL Server Files Manager]中，以滑鼠右鍵按一下[!DNL Temp]欄中的[!DNL Terrain Images.cfg]核取標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL server name]***。

## 為嵌入投影資訊{#section-174f4e00fad84a7ca0c995423dd37ae1}中的影像指定LatLon投影

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Terrain Images.cfg]伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Terrain Images.cfg]的[!DNL Temp]欄中會出現複選標籤。

1. 在[!DNL Temp]欄中按一下新建立的核取標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 [!DNL Terrain Images.cfg]檔案將出現在記事本窗口中。

1. 使用以下示例檔案片段作為參考，編輯「投影資訊」參數。 請務必指定如下突出顯示的投影類型。 有關參數的說明，請參見上一步中的「LatLonProjection參數」表。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
