---
description: 通用橫麥卡托(UTM)投影由8個參數定義。
title: 世界橫麥卡托投影
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# 世界橫麥卡托投影{#universal-transverse-mercator-projections}

通用橫麥卡托(UTM)投影由8個參數定義。

為地形影像層指定通用橫麥卡托投影時，您的地形影像檔案必須與朝影像頂端的偽（投影）對齊，並且與影像右側的偽東對齊。

要為任何地形影像源指定UTM投影，必須在文本編輯器（如記事本）中開啟[!DNL Terrain Images.cfg]檔案，將「投影資訊」參數設定為「VersouseMercatorProjection」，並添加UTM投影的設定。

**指定通用橫麥卡托投影**

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Terrain Images.cfg]*伺服器名稱*&#x200B;列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Terrain Images.cfg]的[!DNL Temp]列中出現複選標籤。

1. 在[!DNL Temp]欄中按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 [!DNL Terrain Images.cfg]檔案將出現在記事本窗口中。

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

| 參數 | 說明 |
|---|---|
| 橢球反扁平化、橢球半長軸 | 用於投影的橢球的參數。 半長軸以公尺為單位指定。 |
| 誤判 | 投影中心子午的假報，以公尺為單位。 對於UTM，這一直是50萬。 |
| 偽標準 | 赤道的偽北線，以公尺為單位。 對於UTM，北半球區為0，南半球區為10,000。 |
| 西北角坐標，東南角坐標 | 影像左上角和右下角的座標（以投影的公尺為單位）。 |
| 主子午線 | 投影中心子午線的經度，以格林尼治以東度指定。 負數可用於指定西度。 |
| 比例因子 | 投影圓柱半徑與橢球的半長軸的比。 對於Universal Versal Mercator(UTM)投影，這始終為0.9996。 |
