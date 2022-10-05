---
description: 請依照下列步驟，使用「傾向分數」視覺效果。
title: 設定傾向分數
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# 設定傾向分數{#setting-up-propensity-scoring}

{{eol}}

請依照下列步驟，使用「傾向分數」視覺效果。

1. 開啟新工作區，然後按一下 **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

   ![](assets/propensity_visualization.png)

1. 設定 **[!UICONTROL Target]** （相依變數）。

   選取以下項目，以設定相依變數：

* **Dimension元素**:在工作區中按一下滑鼠右鍵，然後選取 **[!UICONTROL Table]**. 然後選取Dimension元素作為相依變數。

   或

* **[!UICONTROL Filter Editor]**。按一下 **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]** 以開啟「篩選器編輯器」視覺效果。

   ![](assets/propensity_visualization_filter_editor.png)

   選取Dimension元素或篩選作為相依變數後，按一下 **[!UICONTROL Set Target]**，請輸入描述相依變數的名稱。 然後按一下 **[!UICONTROL OK]** （並確認篩選方塊已反白顯示）以設定Target。

   ![](assets/propensity_visualization_setTarget.png)

   您為目標指定的名稱是將顯示在左窗格中的相依變數。
1. 新增獨立變數。

   使用量度或Dimension元素新增獨立變數。

   ![](assets/propensity_visualization_metrics.png)

* **量度**. 在「傾向分數」工具列中，從 **[!UICONTROL Metrics]** 功能表。

* **Dimension元素**:在工作區中按一下滑鼠右鍵，然後選取 **[!UICONTROL Table]**. 選取一或多個Dimension元素，並拖曳至下方的左欄 **[!UICONTROL Independent Variables]** 或 **[!UICONTROL Element]** 框，使用 `<Ctrl>` + `<Alt>` 鍵。

1. 設定 **[!UICONTROL Training Filter]**. 您可以按一下 **[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]** 從「傾向分數」工具列。 這將提供僅使用您想要分數之訪客所建立之資料的子集。 例如，在上個月造訪的訪客、居住在澳洲的訪客，或檢視特定產品的訪客。

   預設篩選條件為 **[!UICONTROL Train on Everyone]**，但您可以透過啟用 **[!UICONTROL Dimension Elements]** 或使用 **[!UICONTROL Filter Editor]**.

   選取Dimension元素或建立篩選器後，在啟動時按一下 **選項** > **設定培訓篩選器**，輸入要說明篩選器的名稱，然後按一下 **[!UICONTROL OK]**.
1. 確定所有輸入後，按 **[!UICONTROL Go]**.

   ![](assets/propensity_visualization_GO.png)

   計分程式將從多次傳遞資料開始。 然後，它會將結果以橫條圖顯示在百分比線上。
1. 儲存傾向分數。

   從6.1開始，您現在可以選擇使用「儲存傾向分數」：

* 維度
* Dimension和量度

   最後可能會有兩個儲存的檔案，分別是維度和定義的量度。

   >[!NOTE]
   >
   >如果您提交「傾向分數」以進行處理，則只會獲得維度。

   衍生量度是相關聯的平均分數量度。
1. 檢查準確性。

   系統將顯示 **[!UICONTROL Model Complete]** 並在流程完成時生成計分模型。

   按一下右鍵 **[!UICONTROL Model Complete]** 將識別系統所定義計分模型的準確度。 介於0%到100%的值將識別訪客符合 **[!UICONTROL Target]** 變數。

   混淆矩陣通過實際正值(AP)、實際負值(AN)、預計正值(PP)和預計負值(PN)的組合給出四個計數。 這些資料是通過將最終的評分模型應用到20%的預扣測試資料而得到的，我們知道這些資料的真實答案。 如果分數大於50%，則會預測為正面大小寫（符合定義的事件）。

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> 準確度</b> </td> 
   <td colname="col2"> 透過識別所有預測的正確預測來指出模型的準確程度。 <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> 召回</b> </td> 
   <td colname="col2"> 識別重新識別計分模型的能力。 <p><b>TP /(TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> 精準度</b> </td> 
   <td colname="col2">識別不一致的程度。 <p>TP /(TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 開啟 [提升度或增益圖表](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)，或 [模型查看器](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9).

   以滑鼠右鍵按一下 **模型完成** 視覺效果與選取 **[!UICONTROL Lift Chart]**, **[!UICONTROL Gain Chart]**，或 **[!UICONTROL Model Viewer.]**
