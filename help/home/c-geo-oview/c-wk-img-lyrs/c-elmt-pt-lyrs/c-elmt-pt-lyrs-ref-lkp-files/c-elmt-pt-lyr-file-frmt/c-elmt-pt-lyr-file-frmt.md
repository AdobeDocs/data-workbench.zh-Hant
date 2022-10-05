---
description: 格式化有關元素點層檔案的資訊。
title: 元素點層檔案格式
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
exl-id: 125796f6-a447-4f12-bcf2-3e669783cf1e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 5%

---

# 元素點層檔案格式{#element-point-layer-file-format}

{{eol}}

格式化有關元素點層檔案的資訊。

每個元素點層 [!DNL .layer] 引用查找檔案的檔案必須使用以下模板進行格式化：

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Lookup File Name.txt
  Longitude Column = string: Longitude Column Name
  Latitude Column = string: Latitude Column Name
  Name Column = string: Location Column Name
  Key Column = string: Key Column Name
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_B2BC5FE8C80E4680B9A565878192D75B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 資料路徑 </td> 
   <td colname="col2"> 包含經緯度資料的查閱檔案路徑。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 經度欄 </td> 
   <td colname="col2"> 查閱檔案中包含經度資料的欄名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 緯度欄 </td> 
   <td colname="col2"> 查閱檔案中包含緯度資料的欄名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名稱欄 </td> 
   <td colname="col2"> 選填。查閱檔案中欄的名稱，包含經緯度資料所代表之位置的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 索引鍵欄 </td> 
   <td colname="col2"> <p>查閱檔案中包含共同索引鍵資料的欄名稱，可讓Data Workbench伺服器將查詢檔案中的資料整合至資料集。 這必須是查閱檔案中的第一欄。 </p> <p>此欄中的每一列都是維度的元素。 此維度必須定義於 <span class="filepath"> Transformation.cfg</span> 檔案或轉換資料集包含檔案，並在此檔案的Dimension參數中指定。 如需轉換組態檔的詳細資訊，請參閱 <i>資料集組態指南</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 維度 </td> 
   <td colname="col2">維的名稱（在轉換配置檔案中定義）包含與 <span class="wintitle"> 金鑰</span> 欄。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度 </td> 
   <td colname="col2"> 在Dimension參數中指定的維度上評估的量度名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 規模 </td> 
   <td colname="col2"> 選填。用於調整圖層中點大小的值。 預設值為 100。值越大，點越大，值越小，點越小。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 色彩 </td> 
   <td colname="col2"> 選填。RGB顏色向量，以（紅色、綠色、藍色）表示。 對於向量中的每種顏色，可以輸入一個0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 呈現模式 </td> 
   <td colname="col2"> <p>選填。表示要用於圖層的呈現模式的整數值。 三種可用模式如下： 
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">呈現模式1。 點大小定義在螢幕空間中（點相對於電腦螢幕保持恆定大小）。 點是使用多邊形呈現的，因此點大小沒有上限。 這是預設的呈現模式。 </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">呈現模式2。 點大小定義於世界空間（點相對於地球保持恆定大小）。 點是使用多邊形呈現的，因此點大小沒有上限。 </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">呈現模式3。 點大小在螢幕空間中定義。 點使用OpenGL平滑點來呈現。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

此 [!DNL Zip Points.layer] 檔案的格式如下：

```
Layer = ElementPointLayer:
  Data Paths = vector: 1 items
    0 = Path: Maps\\Zip Points.txt
  Longitude Column = string: LONGITUDE
  Latitude Column = string: LATITUDE
  Name Column = string: NAME
  Key Column = string: ZIP_CODE
  Dimension = ref: wdata/model/dim/Zipcode
  Metric = ref: wdata/model/metric/Sessions
```
