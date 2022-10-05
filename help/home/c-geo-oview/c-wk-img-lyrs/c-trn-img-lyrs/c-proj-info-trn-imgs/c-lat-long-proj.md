---
description: Terrain Images.cfg檔案中的經緯度投影格式(LatLonProjection)是由經緯度四個參數所定義。
title: 經緯度投影
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
exl-id: 67ebc7a8-3046-4524-b3a0-0b6da2f235fc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 2%

---

# 經緯度投影{#latitude-longitude-projections}

{{eol}}

Terrain Images.cfg檔案中的經緯度投影格式(LatLonProjection)是由經緯度四個參數所定義。

要為未投影的影像（原始未投影點陣圖和常規影像，未投影）指定LatLonProjection，可在 [!DNL Terrain Images.cfg] data workbench中的視窗。 請參閱 [為未投影的影像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a).

要為包含嵌入投影資訊的影像指定LatLonProjection，必須開啟 [!DNL Terrain Images.cfg] 在文本編輯器（如記事本）中，將「投影資訊」參數設定為「LatLonProjection」，並添加LatLonProjection的設定。 請參閱 [要為嵌入投影資訊中的影像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [為未投影的影像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [要為嵌入投影資訊中的影像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 為未投影的影像指定LatLonProjection {#section-26554eefe645481faba68396fa13756a}

1. 開啟 [!DNL Terrain Images.cfg] 資料工作台中的檔案，並新增地形影像層來源，如 [定義地形影像層](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf).

1. 使用下列參數表作為指南編輯「投影資訊」參數：

   | 參數 | 說明 |
   |---|---|
   | Lat0 | 影像上邊緣的緯度，以度為單位，其中90是北極，-90是南極。 |
   | Lat1 | 影像底邊的緯度。 |
   | Lon0 | 影像左邊的經度，以度為單位，正數為東，負數為西經。 |
   | Lon1 | 影像右側邊緣的經度。 |

1. 按一下滑鼠右鍵以儲存檔案 **[!UICONTROL (modified)]** 按一下 **[!UICONTROL Save]**.

1. 若要將本機所做的變更儲存至Data Workbench伺服器電腦，請前往 [!DNL Server Files Manager]，按一下右鍵的複選標籤 [!DNL Terrain Images.cfg] 在 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## 為嵌入投影資訊內的影像指定LatLon投影 {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. 在 [!DNL Server Files Manager]，按一下 **[!UICONTROL Components]** 來檢視其內容。 此 [!DNL Terrain Images.cfg] 檔案位於此目錄中。

1. 按一下右鍵伺服器名稱列中的複選標籤， [!DNL Terrain Images.cfg]，然後按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Terrain Images.cfg].

1. 在 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 此 [!DNL Terrain Images.cfg] 檔案將出現在記事本窗口中。

1. 使用以下示例檔案片段作為指南編輯「投影資訊」參數。 請務必指定投影類型，如下面突出顯示。 有關參數的說明，請參閱上一步過程中的LatLonProjection參數表。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```
