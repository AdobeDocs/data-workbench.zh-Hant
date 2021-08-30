---
description: 使用具有新取樣和視覺效果功能的回歸樹選項來評估決策樹。
title: 決策樹的迴歸樹選項
uuid: 1e3b5d5f-1fed-49c9-9a4d-d220c28075ac
exl-id: e5f8d525-1530-4169-b246-cdaf30e984c0
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 3%

---

# 決策樹的迴歸樹選項{#regression-tree-option-for-decision-tree}

使用具有新取樣和視覺效果功能的回歸樹選項來評估決策樹。

以滑鼠右鍵按一下「回歸樹」選項，然後在「決策樹」視覺效果中選取「選項」>「**回歸樹」**，以評估決策樹。

**更新的決策樹產生器**:介紹了新的決策樹建 [立算法](https://experienceleague.adobe.com/docs/data-workbench/using/client/analysis-visualizations/decision-trees/c-decision-trees.html)。它可處理更一般的資料，並提供更具資訊量的視覺效果，以提高預測的精度。

**改善的資料取樣模組**:更新的自適應抽樣方案有助於決策樹和傾向分數獲得更高的精度結果。

![](assets/CART-RegressionTreeOptions.jpg)

綠色和紅色表示true或false。 顏色的飽和度（例如深紅色與淺紅色）用於指示概率。 例如，深紅色的節點有很高的假概率，而紅色淺紅色的節點有較低的假概率。 深綠色的節點成為真的可能性很高。

所有決策樹都具有不同的分支寬度，以指示樹的該分支的流量級別。

在「決策樹」視覺效果中，按一下滑鼠右鍵並選取「選項」>「**回歸樹」**。 選取後，會提供其他設定：

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
   <td colname="col2"> <p>選擇此選項將不會使用多次特徵（如原始決策樹） — 因此，如果您有五個輸入，則樹將不超過五個級別，並且樹結構將類似於決策樹（但要複雜一些）。 此選項只使用一次每個功能（如原始決策樹），即可加快樹的生成速度。 使用此功能是預設設定。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>回歸樹級別設定  </b> </p> </td> 
   <td colname="col2"> <p>此選項可控制回歸樹的複雜性。 根據您的資料，您可能需要建立<i>Fine</i>樹（結構複雜且節點較多），才能獲得更有意義的樹分類。 如果您有大量資料，則相對較粗的<i></i>樹（較少的樹節點）可以正常工作。 </p> <p> <p>注意：預設設定為<i>典型</i>。 有些極端情況下，<i>Typical</i>設定也無法正常運作，而<i>Coarse</i>或<i>Fine</i>設定可提供更佳的資料檢視。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>好</i>:最複雜的樹狀結構，具有最精細的報表層級和最多的分支。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>典型</i>:粒度和分支的平均層級。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p><i>粗</i>:最不複雜的樹，定義的類別最少，分支最少。 </p> </td> 
  </tr> 
 </tbody> 
</table>
