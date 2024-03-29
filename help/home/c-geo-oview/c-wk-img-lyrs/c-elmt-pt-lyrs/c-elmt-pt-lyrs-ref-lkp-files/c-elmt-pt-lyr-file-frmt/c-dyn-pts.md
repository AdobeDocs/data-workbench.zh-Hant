---
description: 使用動態點建立元素點層時，經緯度資料會內嵌在維度的每個元素中。
title: 使用動態點定義元素點層
uuid: 5f1b4638-fe45-40be-b963-18dcd5d09afa
exl-id: ad849fe7-b909-40ef-835f-f1764e008de9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 7%

---

# 使用動態點定義元素點層{#defining-element-point-layers-using-dynamic-points}

{{eol}}

使用動態點建立元素點層時，經緯度資料會內嵌在維度的每個元素中。

若要使用動態點定義元素點層，必須建立或已具備下列功能：

* **維度**，定義於 [!DNL Transformation.cfg] 檔案或轉換資料集包含檔案，其中每個元素都包含字串「latitude,longitude」或「latitude,longitude,name」。

   有關建立維的步驟，請參閱 *資料集組態指南*.

* **圖層檔案** 指定相關維。

   有關所需圖層檔案格式的詳細資訊，請參見 [元素點層檔案格式](../../../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-elmt-pt-lyr-file-frmt.md#concept-678a95cb69644105a7af1b86ad5a5981).

>[!NOTE]
>
>使用時 [!DNL Dynamic Points]，則必須確保層檔案中指定的維的基數合理。 如果資料集的每一列有不同的經緯度，維度會快速填滿，大部分列會落入「小元素」元素中。 因為「小元素」元素沒有經緯度，所以不會出現在地球上。

## 元素點層檔案格式 {#section-bbcc2baa2f754dba81eba93339a97cbd}

使用動態點的每個元素點層檔案都必須使用以下模板進行格式化：

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_71AD13D7A9234782A4495DFBBD959F76"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 維度 </td> 
   <td colname="col2"> <p>維度的名稱（在轉換設定檔案中定義），其中必須包含字串為「latitude,longitude」或「latitude,longitude,name」的元素，如下列範例所示： 
     <ul id="ul_49069B74AF5A4CE28E20BB3B98BB2D89"> 
      <li id="li_296010E3A513424A86AFA09E4DA2DFA4">37.5181,-77.1903 </li> 
      <li id="li_352D380B55044DD5AAB9B6FF8335AAC6">35.3317,-77.8126，某處 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度 </td> 
   <td colname="col2"> 在Dimension參數中指定的維度上評估的量度名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 動態點 </td> 
   <td colname="col2"> 啟用動態點。 設為true。 </td> 
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
     <ul id="ul_771F0E43E3CD45259918520F092BCCE4"> 
      <li id="li_2B4CF2EC50174143AAD589A08C7457F8">呈現模式1。 點大小定義在螢幕空間中（點相對於電腦螢幕保持恆定大小）。 點是使用多邊形呈現的，因此點大小沒有上限。 這是預設的呈現模式。 </li> 
      <li id="li_5F0737A941474EF5898735ECD0563D8D">呈現模式2。 點大小定義於世界空間（點相對於地球保持恆定大小）。 點是使用多邊形呈現的，因此點大小沒有上限。 </li> 
      <li id="li_4B9EDE5FFA8348B9A50E5232CEB98F17">呈現模式3。 點大小在螢幕空間中定義。 點使用OpenGL平滑點來呈現。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

此 [!DNL IP Coordinates.layer] 檔案的格式如下：

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
