---
description: 資源監視器向量包含記憶體預算監視器和查詢數監視器。
title: 查詢佇列資源監視器
uuid: 6b516bed-7f9a-4821-869e-19e720f20313
exl-id: 6d445a4d-a415-41ce-9d45-1bdd0e726edd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# 查詢佇列資源監視器{#query-queue-resource-monitors}

資源監視器向量包含記憶體預算監視器和查詢數監視器。

下表描述了用於查詢隊列的資源監視欄位。

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
   <td colname="col3"> <p>監視當前用戶組使用的查詢記憶體。 如果當前使用量介於低閾值和高閾值之間，則不計畫任何新串流，直到記憶體使用量返回到低閾值以下（例如，由於用戶關閉其工作區）。 排定的束團可以增長。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高臨界值 </p> </td> 
   <td colname="col2"> <p>兩次 </p> </td> 
   <td colname="col3"> <p>記憶體使用率的高臨界值（位元組）。 如果記憶體使用率高於此值，則不會發生調度，並且最低優先順序調度的串在一段時間內一次調度一個，直到記憶體使用率低於此值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>低臨界值 </p> </td> 
   <td colname="col2"> <p>兩次 </p> </td> 
   <td colname="col3"> <p>記憶體使用率的低臨界值（位元組）。 如果<span class="wintitle">記憶體預算監視器</span>值低於此值，則允許計畫新串，並允許計畫串增長。 例如，當使用者將視覺效果新增至工作區時，叢集會增加。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反應時間 </p> </td> 
   <td colname="col2"> <p>兩次 </p> </td> 
   <td colname="col3"> <p>平滑記憶體使用量估計的時間常數。 平滑值可避免對使用尖峰的反應。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查詢監視器數 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>監控目前為設定檔排程的查詢總數。 如果查詢總數仍低於「低臨界值」欄位中的值，此資源監視器可讓您排程叢集。 如果查詢總數維持在「高臨界值」欄位中的值以下，則此監視器可允許目前排程的串。 此外，此監視器移除低優先順序的串，以允許排程或增加高優先順序的串。 但是，此設定不會搶佔優先順序大於「不可觸碰優先順序」欄位中指定的簇。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>高臨界值 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>記憶體使用率的高臨界值（位元組）。 如果記憶體使用率高於此值，則不會發生調度，並且最低優先順序的調度串在一段時間內一次調度一個，直到記憶體使用率低於此值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>低臨界值 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>記憶體使用率的低臨界值（位元組）。 如果<span class="wintitle">記憶體預算監視器</span>值低於此值，則可以計畫新的串，並且計畫的串可以增長。 </p> </td> 
  </tr> 
 </tbody> 
</table>
