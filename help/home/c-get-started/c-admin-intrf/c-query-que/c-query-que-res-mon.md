---
description: 資源監視器向量包含記憶體預算監視器和查詢數監視器。
solution: Analytics
title: 查詢隊列資源監視器
topic: Data workbench
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查詢隊列資源監視器{#query-queue-resource-monitors}

資源監視器向量包含記憶體預算監視器和查詢數監視器。

下表說明了用於查詢排隊的資源監視器欄位。

<table id="table_9991EED2647A460FACA2DC80D4973A8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>記憶體預算監視器 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>監視當前用戶組使用的查詢記憶體。 如果當前使用量介於「低閾值」和「高閾值」之間，則在記憶體使用量返回低於「低閾值」值之前，不會計畫任何新的串流，例如，由於用戶關閉其工作區。 預定的束團可以增加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高閾值 </p> </td> 
   <td colname="col2"> <p>雙倍 </p> </td> 
   <td colname="col3"> <p>記憶體使用量的高臨界值（位元組）。 如果記憶體使用量高於此值，則不會進行調度，並且最低優先順序調度的串流在一段時間內一次調度一次，直到記憶體使用量低於此值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>低閾值 </p> </td> 
   <td colname="col2"> <p>雙倍 </p> </td> 
   <td colname="col3"> <p>記憶體使用的低臨界值（位元組）。 如果 <span class="wintitle"> 記憶體預算監視器值低於此值</span> ，則允許安排新的串流，並允許安排的串流增長。 例如，當使用者將視覺化新增至工作區時，叢集會增加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反應時間 </p> </td> 
   <td colname="col2"> <p>雙倍 </p> </td> 
   <td colname="col3"> <p>用於平滑記憶體使用估計的時間常數。 平滑化值可避免對使用尖峰的反應。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查詢監視器數 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>監視當前為配置式計畫的查詢總數。 如果查詢總數仍低於「低閾值」欄位中的值，則此資源監視程式可讓您調度分組。 如果查詢總數維持在「高臨界值」欄位中的值以下，此監視器可讓目前排程的叢集增加。 此外，此顯示器移除低優先順序的串流，以允許排程或增加較高優先順序的串流。 不過，此設定不會搶先優先順序大於「Untouchable Priority」欄位中指定的串。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高閾值 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>記憶體使用量的高臨界值（位元組）。 如果記憶體使用量高於此值，則不會進行調度，並且最低優先順序的調度串會在一段時間內一次調度一個，直到記憶體使用量低於此值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>低閾值 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>記憶體使用的低臨界值（位元組）。 如果 <span class="wintitle"> 記憶體預算監視器</span> (Memory Budget Monitor)值低於此值，則可以計畫新的串流，並可以增加已計畫的串流。 </p> </td> 
  </tr> 
 </tbody> 
</table>

