---
description: 有關元素點圖層檔案的格式資訊。
solution: Analytics
title: 元素點層檔案格式
topic: Data workbench
uuid: a8b3d2f4-0ed2-480d-a2a6-75d43025a579
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 元素點層檔案格式{#element-point-layer-file-format}

有關元素點圖層檔案的格式資訊。

參照查閱檔案 [!DNL .layer] 的每個元素點層檔案都必須使用下列範本格式化：

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
   <td colname="col2"> 包含經度資料的查閱檔案中的欄名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Latitude列 </td> 
   <td colname="col2"> 包含緯度資料的查閱檔案中的欄名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名稱列 </td> 
   <td colname="col2"> 選填。查閱檔案中的欄名稱，包含由經緯度資料所代表的位置名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 鍵列 </td> 
   <td colname="col2"> <p>查閱檔案中包含常用索引鍵資料的欄名稱，可讓資料工作台伺服器將查閱檔案中的資料整合至資料集。 這必須是查閱檔案中的第一欄。 </p> <p>此列中的每一行都是維的元素。 此維必須在 <span class="filepath"></span> Transformation.cfg檔案中定義，或在此檔案的Dimension參數中指定的轉換資料集包含檔案。 有關轉換配置檔案的詳細資訊，請參 <i>閱Dataset Configuration Guide</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 維度 </td> 
   <td colname="col2">維的名稱（在轉換配置檔案中定義），包含與「鍵」列中的資料行對應的 <span class="wintitle"> 元素</span> 。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度 </td> 
   <td colname="col2"> 在「維度」參數中指定的維度上評估的度量名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 規模 </td> 
   <td colname="col2"> 選填。用於調整圖層中點大小的值。 預設值為 100。值越大，點越大，值越小，點越小。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 色彩 </td> 
   <td colname="col2"> 選填。RGB顏色向量，表示為（紅、綠、藍）。 對於向量中的每種顏色，可以輸入0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 演算模式 </td> 
   <td colname="col2"> <p>選填。表示要用於圖層的渲染模式的整數值。 三種可用模式如下： 
     <ul id="ul_CBB26B32505846A39FEB85E831E1C7AB"> 
      <li id="li_B31528A8858C4418ABCDFF0B4EFB25D7">演算模式1。 點大小定義在螢幕空間中（點相對於電腦螢幕的大小保持不變）。 點是使用多邊形來渲染的，因此點大小沒有上限。 這是預設的演算模式。 </li> 
      <li id="li_CA0C3E0DBF004ADBB4D7819C0BF192FC">演算模式2。 點大小定義在世界空間中（點相對於地球保持恆定大小）。 點是使用多邊形來渲染的，因此點大小沒有上限。 </li> 
      <li id="li_8F8729976DDB434D869E81D4381E2688">演算模式3。 點大小定義在螢幕空間中。 點是使用OpenGL平滑點渲染的。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

檔案 [!DNL Zip Points.layer] 的格式如下：

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

