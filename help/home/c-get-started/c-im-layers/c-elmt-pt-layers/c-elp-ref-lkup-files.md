---
description: 建立參考查閱檔案以取得經緯度資料的元素點層時，從查閱檔案中擷取每個元素及其相關聯的經緯度，以取得點的位置。
title: 定義參考查閱檔案的元素點層
uuid: 32c8de7a-4316-4f91-9810-7f584bc7fb0b
exl-id: 2275fa8e-82fe-49e4-ab3e-91ec6ecb6233
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '846'
ht-degree: 3%

---

# 定義參考查閱檔案的元素點層{#define-element-point-layers-referencing-lookup-files}

{{eol}}

建立參考查閱檔案以取得經緯度資料的元素點層時，從查閱檔案中擷取每個元素及其相關聯的經緯度，以取得點的位置。

>[!NOTE]
>
>您可以使用「動態點」功能，將位置的經緯度內嵌於維度的每個元素名稱，而不使用查閱檔案。 請參閱 [使用動態點定義元素點層](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#concept-51adc5e1df8a48e7bd7a582967e4c512).

若要定義參照查閱檔案的元素點層，您必須建立或已具備下列功能：

* **維度** 在 [!DNL Transformation.cfg file] 或 [!DNL transformation dataset include] 檔案。 如需轉換組態檔的相關資訊，請參閱 *資料集組態指南*.

* **查閱檔案** 包含用於繪製每個資料點的資料。 此檔案必須至少包含每個資料點的三列資料：鍵、經度和緯度。 如需查閱檔案所需格式的詳細資訊，請參閱 [元素點層檔案格式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

* **圖層檔案** 這會指定查閱檔案的位置，並識別相關的維度和量度，以及查閱檔案中的索引鍵、經度和緯度欄名稱。 有關所需圖層檔案格式的詳細資訊，請參見 [元素點層檔案格式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elp-ref-lkup-files.md#section-52d7e92be8354d979af9e7a2210b76f2).

   >[!NOTE]
   >
   >此 [!DNL Zip Points.layer] 檔案，隨 [!DNL Geography] 設定檔是可識別 [!DNL Zipcode.dim] 檔案， [!DNL Sessions.metric] 檔案， [!DNL Zip Points.txt] 查閱檔案，以及查閱檔案中索引鍵、經度、緯度和名稱欄的名稱。

## 元素點查閱檔案格式 {#section-0bc8c652c1bd40eb84078f2af71a5c06}

元素點層查閱檔案至少必須包含下列三欄：

* **[!DNL Key]欄：** 此欄應包含通用索引鍵資料，這可讓Data Workbench伺服器將查詢檔案中的資料連結至資料集中的資料。 此 [!DNL key] 欄必須是查閱檔案中的第一欄。 此欄中的每一列都代表維度的元素。

* **[!DNL Longitude]欄：** 此欄應包含 [!DNL Key] 欄。

* **[!DNL Latitude]欄：** 此欄應包含 [!DNL Key] 欄。

* **[!DNL Name]欄（可選）:** 如果您想要指定要在地圖上顯示每個資料點的名稱，您可以包含 [!DNL Name] 欄。

中的每一列 [!DNL Zip Points.txt] 查閱檔案的第一欄中包含郵遞區號，後面接著經度、緯度以及相關的城市名稱。

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

## 元素點層檔案格式 {#section-52d7e92be8354d979af9e7a2210b76f2}

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
   <td colname="col2"> <p>查詢檔案中包含共同索引鍵資料的欄名稱，可讓Data Workbench伺服器將查詢檔案中的資料整合至資料集。 這必須是查閱檔案中的第一欄。 </p> <p>此欄中的每一列都是維度的元素。 此維度必須定義於 <span class="filepath"> Transformation.cfg</span> 檔案或 <span class="wintitle"> 轉換資料集包含</span> 檔案中指定，並在此檔案的Dimension參數中指定。 如需轉換組態檔的詳細資訊，請參閱 <i>資料集組態指南</i>. </p> </td> 
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
     <ul id="ul_F15E43B3BFE54CDD8026837027E25819"> 
      <li id="li_5405D939540E4D0FA7828D2623D72C44">呈現模式1。 點大小定義在螢幕空間中（點相對於電腦螢幕保持恆定大小）。 點是使用多邊形呈現的，因此點大小沒有上限。 這是預設的呈現模式。 </li> 
      <li id="li_61C5AA926777449E8804C7BCE9E46F9B">呈現模式2。 點大小定義於世界空間（點相對於地球保持恆定大小）。 點是使用多邊形呈現的，因此點大小沒有上限。 </li> 
      <li id="li_C00527F959354D3BB7422EFFE1FB5135">呈現模式3。 點大小在螢幕空間中定義。 點使用OpenGL平滑點來呈現。 </li> 
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
