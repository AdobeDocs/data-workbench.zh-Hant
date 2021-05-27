---
description: 您可以建立參考一或多個向量(.vec)檔案的向量層，其中包含定義要在全球繪製的向量的資料。
title: 定義參考向量檔案的向量層
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# 定義參考向量檔案的向量層{#defining-vector-layers-referencing-vector-files}

您可以建立參考一或多個向量(.vec)檔案的向量層，其中包含定義要在全球繪製的向量的資料。

要定義引用一個或多個[!DNL .vec]檔案的向量層，必須具有以下內容：

* 一個或多個[!DNL .vec]檔案，其中包含用於繪製地球上向量的資料。

   >[!NOTE]
   >
   >要獲取要與向量層一起使用的[!DNL .vec]檔案，請聯繫Adobe。

* 指定[!DNL .vec]檔案位置的層檔案。 有關所需的層檔案格式的詳細資訊，請參閱[向量層檔案格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a)。

   >[!NOTE]
   >
   >隨[!DNL Geography]配置檔案提供的[!DNL Boundaries.layer]檔案是參考[!DNL mwnation.vec]、[!DNL mwstate.vec]、[!DNL mwcoast.vec]、[!DNL mwlake.vec]和[!DNL mwisland.vec]檔案的向量層。

## 向量層檔案格式{#section-530d03f41ede4a339aebbb680e15240a}

參考[!DNL .vec]檔案的每個向量層檔案都必須使用下列範本格式化：

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| 參數 | 說明 |
|---|---|
| Vec檔案 | 包含向量資料的[!DNL .vec]檔案的路徑。 |
| 色彩 | RGB顏色向量，表示為（紅、綠、藍）。 對於向量中的每種顏色，可以輸入一個0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 |
| Alpha | 控制在地球上顯示的向量的透明度。 範圍是0到1，其中0是最透明的。 |
| 寬度 | 選填。設定資料的寬度（像素）。 建議的範圍是1到4。 |
| 錯誤因素 | 控制繪製向量的準確程度。 對於較大的值，繪製向量的準確度較低，但速度較快。 預設值為 5。 |

[!DNL Boundaries.layer]檔案的格式如下：

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```
