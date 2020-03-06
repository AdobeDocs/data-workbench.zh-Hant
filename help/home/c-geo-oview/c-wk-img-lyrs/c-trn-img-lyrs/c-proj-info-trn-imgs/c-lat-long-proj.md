---
description: 地形影像。cfg檔案中的經緯度投影格式(LatLonProjection)由經緯度的四個參數定義。
solution: Analytics
title: 經緯度投影
topic: Data workbench
uuid: 0ac947d6-3cd6-4272-96ae-456d2835e63f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 經緯度投影{#latitude-longitude-projections}

地形影像。cfg檔案中的經緯度投影格式(LatLonProjection)由經緯度的四個參數定義。

若要為未投影的影像（原始未投影的點陣圖和一般影像，未投影）指定LatLonProjection，您可以在資料工作台的視窗中輸入LatLonProjection [!DNL Terrain Images.cfg] 的設定。 請參 [閱為未投影的影像指定LatLonProjection](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)。

要為具有嵌入投影資訊的影像指定LatLonProjection，必須在記事本等文本編輯器中開啟檔案，將「投影資訊」參數設定為「LatLonProjection」，並添加LatLonProjection的設定。 [!DNL Terrain Images.cfg] 請參 [閱為嵌入投影資訊中的影像指定LatLonProjection...](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1).

* [為未投影的影像指定LatLon投影](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-26554eefe645481faba68396fa13756a)
* [要為嵌入的投影資訊中的影像指定LatLon投影……](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-lat-long-proj.md#section-174f4e00fad84a7ca0c995423dd37ae1)

## 為未投影的影像指定LatLon投影 {#section-26554eefe645481faba68396fa13756a}

1. 在資料 [!DNL Terrain Images.cfg] 工作台中開啟檔案，並新增地形影像層來源，如 [To define a therrain image layer所述](../../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-trn-img-lyrs.md#concept-8a0a16013e824ac29f35a0349b5d8ccf)。

1. 使用下列參數表作為參考線編輯「投影資訊」參數：

   | 參數 | 說明 |
   |---|---|
   | Lat0 | 影像上緣的緯度，以度為單位，90是北極，-90是南極。 |
   | Lat1 | 影像底部邊緣的緯度。 |
   | Lon0 | 影像左邊緣的經度，以度為單位，正數為東，負數為西經。 |
   | Lon1 | 影像右側邊緣的經度。 |

1. 以滑鼠右鍵按一下視窗頂 **[!UICONTROL (modified)]** 端的檔案，然後按一下以儲存檔案 **[!UICONTROL Save]**。

1. 若要將本機所做的變更儲存至資料工作台伺服器機器，請在欄中 [!DNL Server Files Manager]，以滑鼠右鍵按一下 [!DNL Terrain Images.cfg][!DNL Temp] 的核取標籤，然後按 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*。

## 為嵌入的投影資訊中的影像指定LatLon投影 {#section-174f4e00fad84a7ca0c995423dd37ae1}

1. 在中，單 [!DNL Server Files Manager]擊以 **[!UICONTROL Components]** 查看其內容。 文 [!DNL Terrain Images.cfg] 件位於此目錄中。

1. 按一下右鍵的伺服器名列中的複選標籤， [!DNL Terrain Images.cfg]然後按一下 **[!UICONTROL Make Local]**。 複選標籤會出現在的 [!DNL Temp] 列中 [!DNL Terrain Images.cfg]。

1. 在欄中以滑鼠右鍵按一下新建立的核取標 [!DNL Temp] 記，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Notepad]**。 文 [!DNL Terrain Images.cfg] 件出現在記事本窗口中。

1. 使用以下示例檔案片段作為參考，編輯「投影資訊」參數。 請務必指定如下突出顯示的投影類型。 有關參數的說明，請參見上一步中的「LatLonProjection參數」表。

   ```
   Projection Info = LatLonProjection: 
     Lat0 = double: 90
     Lat1 = double: -90
     Lon0 = double: -180
     Lon1 = double: 180
   ```

