---
description: 使用具有新取樣和視覺化功能的回歸樹選項來評估決策樹。
title: 決策樹的回歸樹選項
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 決策樹的回歸樹選項{#regression-tree-option-for-decision-tree}

使用具有新取樣和視覺化功能的回歸樹選項來評估決策樹。

使用回歸樹選項評估決策樹，方法是在決策樹視覺化中按一下滑鼠右鍵並選取「選 **項」>「回歸樹** 」。

**更新的決策樹產生器**:提出了一種新的決策樹建 [立算法](https://docs.adobe.com/content/help/en/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html)。 它可處理更一般的資料，並提供更豐富的視覺化資訊，以提高預測的精確度。

**改進的資料取樣模組**:更新的自適應抽樣方案有助於決策樹和傾向分數獲得更高的精度結果。

![](assets/CART-RegressionTreeOptions.jpg)

綠色和紅色表示真或假。 顏色的飽和度（例如深紅色與淺紅色）用來表示概率。 例如，深紅色節點的假概率很高，而紅色亮度節點的假概率較低。 深綠色節點的真概率很高。

所有決策樹的分支寬度各不相同，以指示樹的該分支的流量級別。

在「決策樹」視覺化中，以滑鼠右鍵按一下並選取「選項>回 **歸樹」**。 選取後，會提供其他設定：

<table id="table_39E025A3E0B549B4BEDCE0D30A499211"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 回歸設定 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>每項功能僅使用一次</b> </p> </td> 
   <td colname="col2"> <p>選取此選項不會使用多次的功能（如原始決策樹）-因此，如果您有五個輸入，則樹狀結構不會超過五個層級，而樹狀結構看起來會類似於決策樹（但比較複雜）。 此選項只使用一次每個功能（如原始的「決策樹」），即可快速建立樹。 使用此功能是預設設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>回歸樹級別設定 </b> </p> </td> 
   <td colname="col2"> <p>此選項控制回歸樹的複雜性。 視您的資料而定，您可能需要建立 <i>Fine</i> tree（其結構較複雜，節點較多），才能取得更有意義的樹狀分類。 如果您有大量資料，則相對較粗的 <i>Coarse</i> （較不複雜，樹節點較少）可以正常運作。 </p> <p> <p>注意： <i>Typical</i> 為預設設定。 有些極端情況下， <i>Typical</i> （典型）設定效果不佳，而 <i>Coarse</i> （粗） <i>或Fine</i> （精）設定可提供更佳的資料檢視。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>好</i>:最複雜的樹，具有最詳細的報告層級和最多的分支。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>典型值</i>:粒度和分支的平均層級。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>粗</i>:最不複雜的樹，定義的類別和分支最少。 </p> </td> 
  </tr> 
 </tbody> 
</table>

