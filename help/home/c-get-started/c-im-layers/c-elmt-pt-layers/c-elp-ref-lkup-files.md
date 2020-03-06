---
description: 當建立參照查閱檔案以取得經緯度資料的元素點層時，從查閱檔案擷取每個元素及其相關的經緯度資料，以取得點的位置。
solution: Analytics
title: 定義參照查閱檔案的元素點圖層
topic: Data workbench
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定義參照查閱檔案的元素點圖層{#define-element-point-layers-referencing-lookup-files}

當建立參照查閱檔案以取得經緯度資料的元素點層時，從查閱檔案擷取每個元素及其相關的經緯度資料，以取得點的位置。

>[!NOTE]
>
>您可以使用「動態點」功能，而不是使用查閱檔案，此功能會將位置的經緯度內嵌在維度的每個元素名稱中。 請參 [閱使用動態點定義元素點層](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512)。

要定義參照查閱檔案的元素點層，必須建立或已具備以下功能：

* **在或檔案中定義的維**[!DNL Transformation.cfg file][!DNL transformation dataset include] 。 有關轉換配置檔案的資訊，請參 *閱Dataset Configuration Guide*。

* **一個查閱檔案** ，包含用於繪製每個資料點的資料。 此檔案必須至少包含每個資料點的三欄資料：鑰匙，經度和緯度。 如需查閱檔案所需格式的詳細資訊，請參閱「元素點 [層檔案格式」](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)。

* **層檔案** ，它指定查找檔案的位置，並標識查找檔案中的相關維度和度量以及索引鍵、經度和緯度列名。 有關層檔案所需格式的詳細資訊，請參 [閱元素點層檔案格式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2)。

   >[!NOTE]
   >
   >隨配 [!DNL Zip Points.layer] 置檔案提供的檔案是一個元素點層，它標識 [!DNL Geography] 檔案、檔案、 [!DNL Zipcode.dim][!DNL Sessions.metric][!DNL Zip Points.txt] 查閱檔案，以及查閱檔案中鍵、經度、緯度和名稱列的名稱。

## 元素點查閱檔案格式 {#section-0bc8c652c1bd40eb84078f2af71a5c06}

元素點層查閱檔案至少必須包含下列三欄：

* **[!DNL Key]欄：**此欄應包含常用的金鑰資料，這可讓「資料工作台」伺服器將查閱檔案中的資料連接至資料集中的資料。 該[!DNL key]欄必須是查閱檔案中的第一欄。 此列中的每一行都標識維的元素。

* **[!DNL Longitude]欄：**此欄應包含欄中每個資料點的經[!DNL Key]度。

* **[!DNL Latitude]欄：**此列應包含列中每個資料點的[!DNL Key]緯度。

* **[!DNL Name]column(Optional):**如果您想要指定每個資料點在地圖上顯示的名稱，您可以在查閱檔案中[!DNL Name]包含一欄。

查閱檔案中 [!DNL Zip Points.txt] 的每一列都包含第一欄中的「郵遞區號」，後面接著經度、緯度和相關的城市名稱。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## 元素點層檔案格式 {#section-52d7e92be8354d979af9e7a2210b76f2}

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

<table id="table_7287F8869DD04886BE1477CBB11EB796"> 
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
   <td colname="col2"> <p>查閱檔案中包含常用索引鍵資料的欄名稱，可讓資料工作台伺服器將查閱檔案中的資料整合至資料集。 這必須是查閱檔案中的第一欄。 </p> <p>此列中的每一行都是維的元素。 此維必須在 <span class="filepath"> Transformation.cfg檔案中定義，或在</span><span class="wintitle"></span> Transformation Dataset中包含檔案並在此檔案的Dimension參數中指定。 有關轉換配置檔案的詳細資訊，請參 <i>閱Dataset Configuration Guide</i>。 </p> </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">演算模式1。 點大小定義在螢幕空間中（點相對於電腦螢幕的大小保持不變）。 點是使用多邊形來渲染的，因此點大小沒有上限。 這是預設的演算模式。 </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">演算模式2。 點大小定義在世界空間中（點相對於地球保持恆定大小）。 點是使用多邊形來渲染的，因此點大小沒有上限。 </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">演算模式3。 點大小定義在螢幕空間中。 點是使用OpenGL平滑點渲染的。 </li> 
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

