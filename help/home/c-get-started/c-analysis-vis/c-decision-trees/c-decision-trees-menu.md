---
description: 「決策樹」菜單包含設定正面使用案例、篩選器、葉分佈選項、混淆矩陣和其他高級選項的功能。
title: 決策樹選項
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
exl-id: e139562d-4613-4159-a858-2a78a2e896dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 2%

---

# 決策樹選項{#decision-tree-options}

{{eol}}

「決策樹」菜單包含設定正面使用案例、篩選器、葉分佈選項、混淆矩陣和其他高級選項的功能。

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工具欄按鈕 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 開始 </td> 
   <td colname="col2"> 按一下以執行決策樹演算法並顯示視覺效果。 在有輸入項之前，這會變灰。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 重設 </td> 
   <td colname="col2"> 清除輸入和決策樹模型，並重設進程。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 儲存 </td> 
   <td colname="col2"><b>保存決策樹</b>. 您可以以不同格式保存決策樹： 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">預測標籤語言(<b>PMML</b>)，一種基於XML的檔案格式，供應用程式描述和交換決策樹模型。 </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>文字</b> 顯示簡單的列和行，包括true或false、百分比、成員數和輸入值。 </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">A <b>Dimension</b> 與預測結果元素對應的分支。 </li> 
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
   <th colname="col1" class="entry"> 選項功能表 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 設定正大小寫 </td> 
   <td colname="col2"> 將當前工作區選項定義為模型的「正大小寫」。 如果沒有選取項目，則清除大小寫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設定母體篩選 </td> 
   <td colname="col2"> 將目前的工作區選取項目定義為模型的母體篩選，且將從滿足此條件的訪客中提取。 預設值為「所有人」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顯示複雜篩選器說明 </td> 
   <td colname="col2"> 顯示已定義篩選器的說明。 按一下以檢視正面大小寫和填入篩選的篩選指令碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏節點 </td> 
   <td colname="col2"> 隱藏僅佔人口一小部分的節點。 僅當顯示決策樹時才顯示此菜單命令。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 混淆矩陣 </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 選項</span> &gt; <span class="uicontrol"> 混淆矩陣</span> 查看「正確性」、「召回率」、「精確度」和「F分數」值。 接近100%越好。 </p> <p>「混淆矩陣」使用值的組合提供模型的四種準確度計數： 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">實際正數(AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">預計正數(PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">實際負數(AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">預計負數(PN) </li> 
     </ul> </p> <p>提示：通過應用20%測試資料的最終評分模型來獲取這些數字，該模型已被預留，並且已被稱為真實答案。 如果分數大於50%，則會預測為正面大小寫（符合定義的篩選）。 然後，準確度=(TP + TN)/(TP + FP + TN + FN)，召回率= TP /(TP + FN)，精度= TP /(TP + FP)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顯示圖例 </td> 
   <td colname="col2">可讓您開啟或關閉決策樹中的圖例鍵。 <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />僅當顯示決策樹時才顯示此菜單命令。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 進階 </td> 
   <td colname="col2"> 按一下以開啟「高級」菜單，以深入使用決策樹。 有關菜單選項，請參閱下表。 </td> 
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
   <td colname="col2"> <p>控制用於模型建立的訓練集大小。 較大的集需要更長的時間來訓練，較小的集需要更少的時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入標準化 </td> 
   <td colname="col2"> <p> 可讓使用者指定是使用最小值或Z分數技術，將輸入標準化至模型。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMOTE過抽樣系數 </td> 
   <td colname="col2"> 當正面案例在訓練樣本中不經常發生時（小於10%），則使用SMOTE提供額外樣本。 此選項可讓使用者指出要使用SMOTE建立多少個範例。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 葉類分佈閾值 </td> 
   <td colname="col2"> 可讓您在樹狀結構建立過程中設定假定的葉的臨界值。 預設情況下，節點的所有成員必須相同，才能成為葉（在剪枝階段之前）。 </td> 
  </tr> 
 </tbody> 
</table>
