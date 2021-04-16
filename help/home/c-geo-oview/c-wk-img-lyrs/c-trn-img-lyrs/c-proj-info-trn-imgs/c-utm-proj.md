---
description: 通用橫向縮放器(UTM)投影由8個參數定義。
title: 世界橫麥卡托投影
uuid: 55421412-5c68-4a4f-88d6-650d5999a77c
exl-id: 7d7610c3-14e7-474e-b792-ad413c86a2ef
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 3%

---

# 世界橫麥卡托投影{#universal-transverse-mercator-projections}

通用橫向縮放器(UTM)投影由8個參數定義。

為地形影像層指定「通用橫向縮放器」投影時，您的地形影像檔案必須與朝影像頂部向北的假（投影）和向影像右側的假（投影）對齊。

要為任何地形影像源指定UTM投影，必須在文本編輯器（如記事本）中開啟[!DNL Terrain Images.cfg]檔案，將「投影資訊」參數設定為「TransverseMercatorProjection」，並添加UTM投影的設定。

**要指定通用橫向縮放器投影**

1. 在[!DNL Server Files Manager]中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;查看其內容。 [!DNL Terrain Images.cfg]檔案位於此目錄中。

1. 在[!DNL Terrain Images.cfg]的&#x200B;*伺服器名稱*&#x200B;欄中按一下核取標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL Terrain Images.cfg]的[!DNL Temp]欄中會出現複選標籤。

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

| 參數 | 說明 |
|---|---|
| 橢球反平面化橢球半長軸 | 用於投影的橢球參數。 半長軸以米為單位指定。 |
| 誤報 | 投影中心子午的假鑄，以米為單位。 對於UTM，這總是50萬。 |
| False Northing | 赤道的假北方在投影中，以米為單位。 對於UTM，北半球區域為0，南半球區域為10,000。 |
| 西北角坐標，東南角坐標 | 影像左上角和右下角的座標（以投影米數表示）。 |
| Prime Meridian | 投影中心子午線的經度，以格林威治以東的度數指定。 負數可用來指定西向度。 |
| 比例因子 | 投影柱的半徑與橢球的半長軸之比。 對於通用橫向縮放器(UTM)投影，此值一律為0.9996。 |
