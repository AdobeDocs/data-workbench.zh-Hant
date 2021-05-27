---
description: Terrain Images.cfg檔案中的經緯度投影格式(LatLonProjection)是由經緯度四個參數所定義。
title: 經緯度投影
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# 經緯度投影{#latitude-longitude-projections}

Terrain Images.cfg檔案中的經緯度投影格式(LatLonProjection)是由經緯度四個參數所定義。

若要為未投影的影像（原始未投影的點陣圖和一般影像，未投影的影像）指定LatLonProjection，您可以在Data Workbench的[!DNL Terrain Images.cfg]視窗中輸入LatLonProjection的設定。 請參閱[為未投影的影像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)。

要為包含嵌入投影資訊的影像指定LatLonProjection，必須在文本編輯器（如記事本）中開啟[!DNL Terrain Images.cfg]檔案，將「投影資訊」參數設定為「LatLonProjection」，並添加LatLonProjection的設定。 請參閱[為嵌入投影資訊中的影像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)。

* [為未投影的影像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [要為嵌入投影資訊中的影像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 為未投影的影像指定LatLonProjection {#section-26554eefe645481faba68396fa13756a}

1. 在Data Workbench中開啟[!DNL Terrain Images.cfg]檔案，並新增地形影像層來源，如[定義地形影像層](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)所述。

1. 使用下列參數表作為指南編輯「投影資訊」參數：

   | 參數 | 說明 |
   |---|---|
   | Lat0 | 影像上邊緣的緯度，以度為單位，其中90是北極，-90是南極。 |
   | Lat1 | 影像底邊的緯度。 |
   | Lon0 | 影像左邊的經度，以度為單位，正數為東，負數為西經。 |
   | Lon1 | 影像右側邊緣的經度。 |

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**&#x200B;並按一下&#x200B;**[!UICONTROL Save]**&#x200B;以保存檔案。

1. 若要將本機所做的變更儲存至Data Workbench伺服器電腦，請在[!DNL Server Files Manager]中，以滑鼠右鍵按一下[!DNL Temp]欄中的[!DNL Terrain Images.cfg]勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***。

## 為嵌入投影資訊{#section-174f4e00fad84a7ca0c995423dd37ae1}中的影像指定LatLon投影

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Terrain Images.cfg]的伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Terrain Images.cfg]的[!DNL Temp]列中出現複選標籤。

1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 [!DNL Terrain Images.cfg]檔案將出現在記事本窗口中。

1. 使用以下示例檔案片段作為指南編輯「投影資訊」參數。 請務必指定投影類型，如下面突出顯示。 有關參數的說明，請參閱上一步過程中的LatLonProjection參數表。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
