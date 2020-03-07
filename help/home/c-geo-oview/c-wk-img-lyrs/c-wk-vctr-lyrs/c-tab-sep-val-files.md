---
description: 當建立參照Tab分隔值(.tsv)檔案的向量圖層時，會擷取繪圖指示以及。tsv檔案中的經度和緯度資料，以取得向量資料。
solution: Analytics
title: 向量圖層參照Tab分隔值檔案
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 向量圖層參照Tab分隔值檔案{#vector-layers-referencing-tab-separated-values-files}

當建立參照Tab分隔值(.tsv)檔案的向量圖層時，會擷取繪圖指示以及。tsv檔案中的經度和緯度資料，以取得向量資料。

要定義參照檔案的向量 [!DNL .tsv] 層，必須具有以下內容：

* **包含[!DNL .tsv]** 用於繪製全球向量（包括經度和緯度資料）的資料的檔案。 如需檔案所需格式的詳細資訊，請 [!DNL .tsv] 參閱向 [量TSV檔案格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e)。

* **指定檔案位置的層檔案**[!DNL .tsv] 。 有關層檔案所需格式的詳細資訊，請參 [閱向量層檔案格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)。

## 向量TSV檔案格式 {#section-a29012c9ff4444ac8a6d41c68482828e}

檔 [!DNL .tsv] 案必須包含下列三個以標籤分隔的欄：

* **[!DNL Begin]:**此列應指示是否開始新行。 此欄中的值可以是0（不要開始新行）或1（開始新行）。
* **[!DNL Longitude]:**此欄應包含經度值。
* **[!DNL Latitude]:**此列應包含緯度值。

>[!NOTE]
>
>會忽略任何其他欄。

以下是包含向 [!DNL .tsv] 量圖層資料的範例檔案：

![](assets/tsv_vectorlayer.png)

## 向量圖層檔案格式 {#section-c430923f341f4c93852e9f24b61e82bf}

每個參照檔案的向量層 [!DNL .tsv] 檔案必須使用以下模板進行格式化：

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> TSV檔案 </td> 
   <td colname="col2"> <p>包含向量資料 <span class="filepath"> 之。tsv</span> (s)檔案的路徑。 </p> <p>範例： <span class="filepath"> 地圖\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 色彩 </td> 
   <td colname="col2"> RGB顏色向量，表示為（紅、綠、藍）。 對於向量中的每種顏色，可以輸入0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> 控制全球顯示向量的透明度。 範圍是0到1，其中0是最透明的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寬度 </td> 
   <td colname="col2"> 選填。設定資料的寬度（以像素為單位）。 建議的範圍是1到4。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤因素 </td> 
   <td colname="col2"> 控制繪製向量的精確度。 對於較大的值，繪製向量時會較不精確但較快。 預設值為 5。 </td> 
  </tr> 
 </tbody> 
</table>

