---
description: 使用動態點建立元素點層時，緯度和經度資料會內嵌在維度的每個元素中。
title: 使用動態點定義元素點層
uuid: f4b41969-329a-4c33-a8db-8d85597fa577
exl-id: 5f6e264c-5804-47fa-a3ca-8608a3f7e9d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 5%

---

# 使用動態點定義元素點層{#define-element-point-layers-using-dynamic-points}

使用動態點建立元素點層時，緯度和經度資料會內嵌在維度的每個元素中。

要使用動態點定義元素點層，必須建立或已具備以下功能：

* 在[!DNL Transformation.cfg]檔案或[!DNL transformation dataset include]檔案中定義的維度，其中每個元素都包含字串&quot;latitude,lognitude,name&quot;。

   有關建立維的步驟，請參閱&#x200B;*資料集配置指南*。

* 指定相關尺寸的層檔案。

有關層檔案所需格式的詳細資訊，請參閱[元素點層檔案格式](../../../../home/c-get-started/c-im-layers/c-elmt-pt-layers/c-elmt-pt-dyn-pts.md#section-0645fbc761c14bb986f3d6f02df407a0)。

>[!NOTE]
>
>使用[!DNL Dynamic Points]時，必須確保層檔案中指定的尺寸的基數是合理的。 如果資料集的每一列都有不同的經緯度，維度會快速填滿，而大部分的列會落入「小元素」元素中。 由於「小元素」元素沒有經緯度，因此不會出現在地球上。

## 元素點層檔案格式{#section-0645fbc761c14bb986f3d6f02df407a0}

每個使用動態點的元素點層檔案必須使用以下模板進行格式化：

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Dimension Name
  Metric = ref: wdata/model/metric/Metric Name
  Dynamic Points = bool: true
  Scale = double: Scale
  Color = v3d: RGB Color Vector
  Rendering Mode = int: Mode Number
```

<table id="table_8756BDCC49F447C0855BA64BC0078A0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 維度 </td> 
   <td colname="col2"> <p>維的名稱（定義在轉換配置檔案中），它必須包含字串為"latitude,lognitude"或"latitude,lognitude,name"的元素，如以下示例所示： 
     <ul id="ul_CC12F05459C640F5AB3C295932B04F83"> 
      <li id="li_9023CFA04A0F407E9DF0E1A4D71BB18C">37.5181,-77.1903 </li> 
      <li id="li_F002AB3AB98049A4AF1588B51167C7FA">35.3317,-77.8126，某處 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 量度 </td> 
   <td colname="col2"> 在Dimension參數中指定的維度上評估的度量名稱。 </td> 
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
   <td colname="col2"> 選填。RGB顏色向量，表示為（紅、綠、藍）。 對於向量中的每種顏色，可以輸入0.0到1.0的值。例如，(1.0、0.0、0.0)為亮紅色，(0.5、0.5、0.5)為灰色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 演算模式 </td> 
   <td colname="col2"> <p>選填。表示要用於圖層的渲染模式的整數值。 三種可用模式如下： 
     <ul id="ul_C7A74B9B085741C8B7116E4F110DF830"> 
      <li id="li_75CC2BE35C594B6895F743A1967A2E07">演算模式1。 點大小定義在螢幕空間中（點相對於電腦螢幕的大小保持不變）。 點是使用多邊形來渲染的，因此點大小沒有上限。 這是預設的演算模式。 </li> 
      <li id="li_5B19C5B0F59548E28DCE7F7CD319E210">演算模式2。 點大小定義在世界空間中（點相對於地球保持恆定大小）。 點是使用多邊形來渲染的，因此點大小沒有上限。 </li> 
      <li id="li_DF0C9AEFE82642C9BD5AEA79770D2896">演算模式3。 點大小定義在螢幕空間中。 點是使用OpenGL平滑點渲染的。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

[!DNL IP Coordinates.layer]檔案的格式如下：

```
Layer = ElementPointLayer:
  Dimension = ref: wdata/model/dim/Coordinates
  Metric = ref: wdata/model/metric/Visitors
  Dynamic Points = bool: true
```
