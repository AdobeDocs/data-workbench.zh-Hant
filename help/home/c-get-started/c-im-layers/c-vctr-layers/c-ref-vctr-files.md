---
description: 您可以建立參考一或多個向量(.vec)檔案的向量層，其中包含定義要在全球繪製的向量的資料。
title: 定義參考向量檔案的向量層
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# 定義參考向量檔案的向量層{#define-vector-layers-referencing-vector-files}

{{eol}}

您可以建立參考一或多個向量(.vec)檔案的向量層，其中包含定義要在全球繪製的向量的資料。

定義參照一個或多個向量層 [!DNL .vec] 檔案，您必須具備下列條件：

* **一或多個 [!DNL .vec] 檔案** 包含在地球上繪製向量的資料。

   >[!NOTE]
   >
   >若要取得 [!DNL .vec] 要與向量層一起使用的檔案，請聯繫Adobe。

* **圖層檔案** 會指定 [!DNL .vec] 檔案。 有關所需圖層檔案格式的詳細資訊，請參見 [向量層檔案格式](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1).

   >[!NOTE]
   >
   >此 [!DNL Boundaries.layer] 檔案，隨 [!DNL Geography] profile，是參考的向量層 [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]，和 [!DNL mwisland.vec] 檔案。

## 向量層檔案格式 {#section-83a0077cf0c8479b9e7b2939bc761af1}

每個參考的向量層檔案 [!DNL .vec] 檔案必須使用以下模板進行格式化：

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
| Vec檔案 | 路徑至 [!DNL .vec] 包含向量資料的檔案。 |
| 色彩 | RGB顏色向量，以（紅色、綠色、藍色）表示。 對於向量中的每種顏色，可以輸入一個0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 |
| Alpha | 控制在地球上顯示的向量的透明度。 範圍是0到1，其中0是最透明的。 |
| 寬度 | 選填。設定資料的寬度（像素）。 建議的範圍是1到4。 |
| 錯誤因素 | 控制繪製向量的準確程度。 對於較大的值，繪製向量的準確度較低，但速度較快。 預設值為 5。 |

此 [!DNL Boundaries.layer] 檔案的格式如下：

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
