---
description: 建立參考Tab分隔值(.tsv)檔案的向量層時，通過檢索繪圖指令以及.tsv檔案中的經度和緯度資料來獲取向量資料。
title: 參考 Tab 字元分隔值檔案的向量層
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763,7b0b0286-072b-4b31-b6ec-ced322da5236
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# 參考 Tab 字元分隔值檔案的向量層{#vector-layers-referencing-tab-separated-values-files}

建立參考Tab分隔值(.tsv)檔案的向量層時，通過檢索繪圖指令以及.tsv檔案中的經度和緯度資料來獲取向量資料。

要定義參照[!DNL .tsv]檔案的向量層，必須具有以下內容：

* **一 [!DNL .tsv]** 個檔案，包含用來繪製地球向量的資料，包括經度和緯度資料。有關[!DNL .tsv]檔案所需格式的詳細資訊，請參閱[向量TSV檔案格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e)。

* **指定** 檔案位置的層檔 [!DNL .tsv] 案。有關所需的層檔案格式的詳細資訊，請參閱[向量層檔案格式](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)。

## 向量TSV檔案格式{#section-a29012c9ff4444ac8a6d41c68482828e}

[!DNL .tsv]檔案必須包含以下三個以頁簽分隔的列：

* **[!DNL Begin]:** 此欄應指出是否開始新的行。此欄中的值可以是0（不開頭新行）或1（開頭新行）。
* **[!DNL Longitude]:** 此欄應包含經度值。
* **[!DNL Latitude]:** 此欄應包含緯度值。

>[!NOTE]
>
>會忽略任何其他欄。

以下是包含向量層資料的範例[!DNL .tsv]檔案：

![](assets/tsv_vectorlayer.png)

## 向量層檔案格式{#section-c430923f341f4c93852e9f24b61e82bf}

參考[!DNL .tsv]檔案的每個向量層檔案都必須使用下列範本格式化：

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
   <td colname="col2"> <p>包含向量資料的<span class="filepath"> .tsv</span>檔案的路徑。 </p> <p>範例：<span class="filepath"> Maps\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 色彩 </td> 
   <td colname="col2"> RGB顏色向量，表示為（紅、綠、藍）。 對於向量中的每種顏色，可以輸入一個0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alpha </td> 
   <td colname="col2"> 控制在地球上顯示的向量的透明度。 範圍是0到1，其中0是最透明的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 寬度 </td> 
   <td colname="col2"> 選填。設定資料的寬度（像素）。 建議的範圍是1到4。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤因素 </td> 
   <td colname="col2"> 控制繪製向量的準確程度。 對於較大的值，繪製向量的準確度較低，但速度較快。 預設值為 5。 </td> 
  </tr> 
 </tbody> 
</table>
