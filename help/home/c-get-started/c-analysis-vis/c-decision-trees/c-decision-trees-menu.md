---
description: 「決策樹」功能表包含設定正面使用案例、篩選器、葉分佈選項、混淆矩陣和其他進階選項的功能。
title: 決策樹選項
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 決策樹選項{#decision-tree-options}

「決策樹」功能表包含設定正面使用案例、篩選器、葉分佈選項、混淆矩陣和其他進階選項的功能。

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工具列按鈕 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 前往 </td> 
   <td colname="col2"> 按一下以執行決策樹演算法並顯示視覺化。 在有輸入前，此選項會呈灰色顯示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重設 </td> 
   <td colname="col2"> 清除輸入和決策樹模型並重設流程。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 儲存 </td> 
   <td colname="col2"><b>保存決策樹</b>。 可以以不同格式保存決策樹： 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">預測標籤語言(<b>PMML</b>)，一種XML檔案格式，應用程式用來描述和交換決策樹模型。 </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>顯示</b> 「是」或「是」的簡單列和行、百分比、成員數和輸入值的文本。 </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">具有 <b>與預測結果元素</b> 對應的分支的維。 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 選項 </td> 
   <td colname="col2"> 請參閱下表中的「選項」功能表。 </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項菜單 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 設定正面大小寫 </td> 
   <td colname="col2"> 將當前工作區選擇定義為模型的「正大小寫」(Positive Case)。 如果不存在選擇，則清除大小寫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設定人口篩選 </td> 
   <td colname="col2"> 將目前的工作區選擇定義為模型的「人口篩選」，並將從符合此條件的訪客中提取。 預設值為「每個人」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顯示複雜篩選器說明 </td> 
   <td colname="col2"> 顯示已定義篩選器的說明。 按一下以檢視「正面大小寫」和「填入篩選」的篩選指令碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏節點 </td> 
   <td colname="col2"> 隱藏只佔人口一小部分的節點。 僅當顯示決策樹時，才會顯示此菜單命令。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 混淆矩陣 </td> 
   <td colname="col2"> <p>按一 <span class="uicontrol"> 下「選項</span> &gt;混淆矩陣 <span class="uicontrol"></span> 」，以檢視「正確性」、「召回率」、「精確度」和「F-Score」值。 接近100%越好。 </p> <p>「混淆矩陣」使用值組合，提供模型的4種精確度計數： 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">實際正數(AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">預計正數(PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">實際負值(AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">預計負值(PN) </li> 
     </ul> </p> <p>提示： 這些資料是通過應用對20%測試資料的最終評分模型得到的，該模型已被稱為真實答案。 如果分數大於50%，則會預測為正面案例（與定義的篩選器相符）。 然後，精度=(TP + TN)/(TP + FP + TN + FN)，召回率= TP /(TP + FN)，精度= TP /(TP + FN)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顯示圖例 </td> 
   <td colname="col2">允許您在決策樹中開啟和關閉圖例鍵。 <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />僅當顯示決策樹時，才會顯示此菜單命令。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 進階 </td> 
   <td colname="col2"> 按一下以開啟「高級」(Advanced)菜單，以深入使用「決策樹」。 請參閱下表以取得功能表選項。 </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 進階功能表 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 訓練集大小 </td> 
   <td colname="col2"> <p>控制用於模型建立的訓練集大小。 較大的組訓練時間較長，較小的組訓練時間較短。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入標準化 </td> 
   <td colname="col2"> <p> 允許使用者指定是否使用Min-Max或Z分數技術來標準化模型的輸入。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMOTE過採樣系數 </td> 
   <td colname="col2"> 當訓練樣本中不常（小於10%）發生「陽性案例」時，會使用SMOTE來提供額外樣本。 此選項可讓使用者指出要使用SMOTE建立的範例數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 葉類分佈閾值 </td> 
   <td colname="col2"> 允許您在樹構建過程中設定假定葉的閾值。 預設情況下，節點的所有成員必須相同，才能成為葉（在修剪階段之前）。 </td> 
  </tr> 
 </tbody> 
</table>

