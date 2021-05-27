---
description: 定義用戶組參數的表。
title: 查詢佇列使用者群組
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# 查詢佇列使用者群組{#query-queue-user-groups}

定義用戶組參數的表。

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>名稱 </p> </td> 
   <td colname="col2"> <p>字串 </p> </td> 
   <td colname="col3"> <p>使用者群組的使用者定義名稱，例如分析師。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>原則 </p> </td> 
   <td colname="col2"> <p>向量 </p> </td> 
   <td colname="col3"> <p>指定策略類型。 按一下右鍵以選擇「標準策略」或「每日計畫」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準政策 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>標準策略可確保低優先順序的用戶逐漸地向隊列上移動並調度，即使高優先順序的用戶進入隊列也是如此。 您可以在組中添加多個相同類型的策略，其效果是累積的。 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>優先順序限制：</b> 優先順序未增加的上限。最大優先順序值。 您可以使用此值將此策略生成的優先順序保持在特定範圍(例如，這樣，某些其他用戶組的優先順序總是較高，或者它們不會高於不可觸碰優先順序。 </li> 
     </ul> </p> <p> <b>標準政策增量</b> </p> <p>標準策略的增量設定會隨著時間的流逝而增加查詢堆的優先順序。 這不會強制排程串，但您可以使用這些設定來排定等候了很久的使用者的優先順序。 佇列的參數會影響目前已排入佇列的查詢（例如因資源不足而無法完成等待）。 排程的參數會影響正在回答的查詢。 查詢的優先順序會以在適當的增量和增量間隔欄位中指定的數字增加： 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>佇列增量： </b> 在佇列時，設定每次更新的優先順序增量。此設定可確保將低優先順序使用者移至排程佇列上方。 </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>佇列增量間隔： </b> 設定佇列時更新之間的秒數。 </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>已排程增量： </b> 設定已排程時每次更新的優先順序增量。 </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>已排程的增量間隔： </b> 設定已排程時兩次更新之間的秒數。 <p> <p>注意： 將排隊簇的增量和間隔更新速率設定得高於調度簇的增量和間隔更新速率可能會引起振蕩。 (例如，假設您將「排隊增量」值設定為100，「排程增量」設定為0，並將「排隊增量間隔」值設定為1，「不可觸碰優先順序」設定為高。 如果兩個查詢組以0作為基本優先順序傳入，並且資源不足以同時運行兩個查詢，則計畫其中一個查詢。 一秒後，未排程的查詢的優先順序為100，並搶先排程的查詢。 再過兩秒，被搶佔的優先順序為200，兩個交換機再次置於位置。 兩個查詢都不完成，因為每兩秒計算一次的查詢就會被搶佔，這樣另一個查詢就可以運行。) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每日計劃策略 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>可讓您變更一天中特定時間的優先順序。 此計畫對於自動化客戶端（如<span class="wintitle">報表伺服器</span>）以及系統用戶在不同時區中生活時非常有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>變更 </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>按一下滑鼠右鍵可新增排程的優先順序變更。 「變更時間」是發生變更的時間。 格式為小時：分鐘/上午。 如果未輸入AM或PM，則系統使用軍事時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>優先順序限制 </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>因變更而產生的最大優先順序值。 「優先順序變更」是新增至優先順序的金額。 例如，值0會傳回預設優先順序。 任何其他值都會產生預設優先順序加上此數字的優先順序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者 </p> </td> 
   <td colname="col2"> <p>向量 </p> </td> 
   <td colname="col3"> <p>列出屬於群組的成員的使用者。 </p> <p> <b>名稱： </b> 使用者的名稱，如使用者憑證的「一般名稱」欄位中所顯示。 </p> <p> <b>額外優先順序： </b> 提供使用者群組的基本優先順序的額外優先順序，以決定該使用者的起始優先順序。 </p> </td> 
  </tr> 
 </tbody> 
</table>
