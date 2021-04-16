---
description: 定義用戶組參數的表。
title: 查詢佇列使用者群組
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
translation-type: tm+mt
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
   <td colname="col1"> <p>策略 </p> </td> 
   <td colname="col2"> <p>向量 </p> </td> 
   <td colname="col3"> <p>指定策略類型。 按一下右鍵以選擇「標準策略」或「每日計畫」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準政策 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>標準原則可確保低優先順序的使用者會遞增地移至佇列並排程，即使高優先順序的使用者會進入佇列。 您可以在群組中新增多個相同類型的原則，其效果是累積的。 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>優先順序限</b> 制：優先順序未增加的上限。最大優先順序值。 您可以使用此值將此原則產生的優先順序保留在特定範圍內(例如，讓某些其他使用者群組的優先順序永遠較高，或不會高於Untouchable Priority。 </li> 
     </ul> </p> <p> <b>標準政策增量</b> </p> <p>標準原則的增量設定會隨著時間流逝而增加查詢串的優先順序。 這不會強制排程串，但您可以使用這些設定來排定等候了很長時間的使用者的優先順序。 佇列參數會影響目前佇列的查詢（例如由於資源不足而無法完成佇列）。 排程的參數會影響正在回答的查詢。 查詢的優先順序會隨著在相應增量和增量間隔欄位中指定的數字而增加： 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>排隊增量：</b> 在排隊時設定每次更新的優先順序增量。此設定可確保低優先順序使用者移至排程佇列上方。 </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>排隊增量間隔：</b> 設定排隊時更新之間的秒數。 </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>計畫增量：</b> 在計畫時設定每次更新的優先順序增量。 </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>排程增量間隔：</b> 設定排程時兩次更新的秒數。 <p> <p>注意： 將排隊串流的增量和間隔更新速率設定為高於計畫串流的增量和間隔更新速率可能會引起振蕩。 (例如，假設您將「排隊增量」值設定為100，將「計畫增量」設定為0，將「排隊增量間隔」值設定為1，將「賤民優先順序」設定為高。 如果兩個查詢串的基本優先順序為0，並且沒有足夠的資源同時運行兩個查詢，則會計畫其中一個查詢。 一秒後，未排程的查詢的優先順序為100，並搶先排程的查詢。 再過兩秒，搶佔的優先順序現在為200，兩個交換機再次置位。 兩個查詢都不完成，因為每兩秒計算的查詢都會被搶佔，以便運行其他查詢。) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>每日計劃策略 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>可讓您在一天中的特定時間變更優先順序。 此計畫對於自動化客戶端（如<span class="wintitle">報告伺服器</span>）和系統用戶生活在不同時區時非常有用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>變更 </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>按一下滑鼠右鍵可新增排程的優先順序變更。 「更改時間」是發生更改的時間。 格式為小時：分鐘AM/PM。 如果未輸入AM或PM，則系統使用軍事時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>優先順序限制 </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>由更改引起的最大優先順序值。 「優先順序變更」是新增至優先順序的金額。 例如，值0會返回預設優先順序。 任何其他值都會產生預設優先順序加上此數字的優先順序。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>使用者 </p> </td> 
   <td colname="col2"> <p>向量 </p> </td> 
   <td colname="col3"> <p>列出屬於群組成員的使用者。 </p> <p> <b>名稱：</b> 使用者憑證中「公用名稱」欄位中所顯示的使用者名稱。 </p> <p> <b>額外優先順</b> 序：提供使用者群組基本優先順序的額外優先順序，以決定該使用者的起始優先順序。 </p> </td> 
  </tr> 
 </tbody> 
</table>
