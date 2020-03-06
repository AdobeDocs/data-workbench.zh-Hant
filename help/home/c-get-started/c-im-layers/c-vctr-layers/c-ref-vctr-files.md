---
description: 您可以建立參照一或多個向量(.vec)檔案的向量圖層，其中包含定義要在全球繪製向量的資料。
solution: Analytics
title: 定義參照向量檔案的向量圖層
topic: Data workbench
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定義參照向量檔案的向量圖層{#define-vector-layers-referencing-vector-files}

您可以建立參照一或多個向量(.vec)檔案的向量圖層，其中包含定義要在全球繪製向量的資料。

要定義參照一個或多個檔案的向 [!DNL .vec] 量層，必須具有以下內容：

* **一或多個[!DNL .vec]檔案** ，其中包含用來在全球繪製向量的資料。

   >[!NOTE]
   >
   >若要取得 [!DNL .vec] 要與向量圖層搭配使用的檔案，請與Adobe聯絡。

* **指定檔案位置的層檔案**[!DNL .vec] 。 有關層檔案所需格式的詳細資訊，請參 [閱向量層檔案格式](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1)。

   >[!NOTE]
   >
   >隨配 [!DNL Boundaries.layer] 置檔案提供的文 [!DNL Geography] 件是參照、、、、和檔案 [!DNL mwnation.vec]的向量 [!DNL mwstate.vec]層 [!DNL mwcoast.vec][!DNL mwlake.vec][!DNL mwisland.vec] 。

## 向量圖層檔案格式 {#section-83a0077cf0c8479b9e7b2939bc761af1}

每個參照檔案的向量層 [!DNL .vec] 檔案必須使用以下模板進行格式化：

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
| Vec檔案 | 包含向量資料 [!DNL .vec] 之檔案的路徑。 |
| 色彩 | RGB顏色向量，表示為（紅、綠、藍）。 對於向量中的每種顏色，可以輸入0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 |
| Alpha | 控制全球顯示向量的透明度。 範圍是0到1，其中0是最透明的。 |
| 寬度 | 選填。設定資料的寬度（以像素為單位）。 建議的範圍是1到4。 |
| 錯誤因素 | 控制繪製向量的精確度。 對於較大的值，繪製向量時會較不精確但較快。 預設值為 5。 |

檔案 [!DNL Boundaries.layer] 的格式如下：

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

