---
description: 請依照下列步驟，使用「傾向分數」視覺化。
title: 設定傾向分數
uuid: afc9aada-3bf9-4ce6-8c43-a955771065b4
exl-id: e16a7062-636e-44a9-a07d-343d48bf1b4c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 2%

---

# 設定傾向分數{#setting-up-propensity-scoring}

請依照下列步驟，使用「傾向分數」視覺化。

1. 開啟新工作區，然後按一下「**[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**」。

   ![](assets/propensity_visualization.png)

1. 設定&#x200B;**[!UICONTROL Target]**（相依變數）。

   通過選擇：

* **Dimension元素**:在工作區中按一下滑鼠右鍵，然後選取 **[!UICONTROL Table]**。然後選取Dimension元素作為相依變數。

   或

* **[!UICONTROL Filter Editor]**。按一下「**[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Filter Editor]**」以開啟「篩選編輯器」視覺化。

   ![](assets/propensity_visualization_filter_editor.png)

   選擇Dimension元素或篩選器作為相依變數後，按一下&#x200B;**[!UICONTROL Set Target]** ，輸入用於描述相依變數的名稱。 然後按一下&#x200B;**[!UICONTROL OK]**（並確定篩選方塊已反白顯示）以設定Target。

   ![](assets/propensity_visualization_setTarget.png)

   您為目標提供的名稱是將顯示在左側窗格中的從屬變數。
1. 新增獨立變數。

   使用「量度」或「Dimension元素」新增獨立變數。

   ![](assets/propensity_visualization_metrics.png)

* **量度**. 從「傾向分數」工具列，從&#x200B;**[!UICONTROL Metrics]**&#x200B;選單中選取量度。

* **Dimension元素**:在工作區中按一下滑鼠右鍵，然後選取 **[!UICONTROL Table]**。選擇一個或多個Dimension元素，然後使用`<Ctrl>` + `<Alt>`鍵拖動到&#x200B;**[!UICONTROL Independent Variables]**&#x200B;下的左列或&#x200B;**[!UICONTROL Element]**&#x200B;框。

1. 設定 **[!UICONTROL Training Filter]**. 您可以按一下「傾向評分」工具列中的&#x200B;**[!UICONTROL Options]** > **[!UICONTROL Set Training Filter]**&#x200B;來定義要評分的訪客集。 這將提供僅使用您想要分數的訪客所建立之資料子集。 例如，在上個月瀏覽的訪客、居住於澳洲的訪客或檢視特定產品的訪客。

   預設篩選器為&#x200B;**[!UICONTROL Train on Everyone]**，但您可以在表格中啟動&#x200B;**[!UICONTROL Dimension Elements]**，或使用&#x200B;**[!UICONTROL Filter Editor]**&#x200B;建立篩選器來變更。

   在選擇Dimension元素或建立篩選器後，在啟動時，按一下「選項&#x200B;**** > **設定訓練篩選器**」，輸入描述篩選器的名稱，然後按一下「**[!UICONTROL OK]**」。
1. 確定所有輸入後，按&#x200B;**[!UICONTROL Go]**&#x200B;鍵。

   ![](assets/propensity_visualization_GO.png)

   計分程式將從多次傳遞資料開始。 然後，它會以橫條圖的形式顯示結果，並且以百分比線為單位。
1. 儲存傾向分數。

   從6.1開始，您現在可以在使用「儲存傾向分數」時選擇：

* 維度
* Dimension與量度

   您最後可以有兩個儲存的檔案，一個維度和一個定義的度量。

   >[!NOTE]
   >
   >如果您提交「傾向分數」以進行處理，則只會得到維度。

   衍生量度是關聯的平均分數量度。
1. 檢查準確性。

   系統將顯示&#x200B;**[!UICONTROL Model Complete]**&#x200B;並在流程完成時生成計分模型。

   在&#x200B;**[!UICONTROL Model Complete]**&#x200B;上按一下滑鼠右鍵，可識別由系統定義之計分模型的精確度。 介於0%到100%的值會識別訪客符合&#x200B;**[!UICONTROL Target]**&#x200B;變數的可能性。

   混淆矩陣通過實際正(AP)、實際負(AN)、預測正(PP)和預測負(PN)的組合給出四種計數。 通過對20%的預留測試資料應用最終的評分模型，得到了這些資料，並且我們知道其真實答案。 如果分數大於50%，則會預測為正面案例（符合已定義的事件）。

   ![](assets/propensity_lift_gain_1.png)

<table id="table_154BDD6D294C4ED1B8C15EC33B74B199"> 
 <tbody> 
  <tr> 
   <td colname="col1"><b> 準確度</b> </td> 
   <td colname="col2"> 識別所有預測的正確預測，以指出模型的精確性。 <p>(TP + TN)/(TP + FP + TN + FN) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> 召回</b> </td> 
   <td colname="col2"> 識別重新識別計分模型的能力。 <p><b>TP /(TP + FN)</b> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> 精確度</b> </td> 
   <td colname="col2">識別差異程度。 <p>TP /(TP + FP) </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 開啟[提升度或增益圖表](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)或[模型檢視器](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-9f2593a8218140b7bd132a4c74e159f9)。

   在&#x200B;**Model Complete**&#x200B;視覺化上按一下滑鼠右鍵，然後選取&#x200B;**[!UICONTROL Lift Chart]**、**[!UICONTROL Gain Chart]**&#x200B;或&#x200B;**[!UICONTROL Model Viewer.]**
