---
description: 選取輸入變數、叢集數目和目標人口（如果需要），以定義資料集中的叢集。
solution: Analytics
title: 建立叢集
topic: Data workbench
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 建立叢集{#building-clusters}

選取輸入變數、叢集數目和目標人口（如果需要），以定義資料集中的叢集。

**建立叢集**

1. 開啟 **[!UICONTROL Cluster Builder]**.

   按一 **下視覺化** > **Predictive Analytics** > **叢集** > Cluster Builder ****。

   ![](assets/cluster-builder-step1.png)

1. 選取輸入變數。

   * 從工具列的選 **[!UICONTROL Input Variables]** 單中選取，將量 **[!UICONTROL Metric]** 度新增至清單。

      ![](assets/cluster_metric_select.png)

   * 將維元素從「維 **[!UICONTROL Input Variables]** 」的表中拖動，將其添加到清單中。

      按下 **[!UICONTROL Ctrl + Alt]** 並拖曳選取的維度元素至 **[!UICONTROL Input Variables]** 清單或工具列 **[!UICONTROL Element]** 的方塊中。

      ![](assets/cluster_dim_select.png)
   依預設，會在整個資料集上執行叢集。 您可以在左窗格中查看所有輸入 **[!UICONTROL Preprocessing]** 變數。
1. 使用功 **[!UICONTROL Options]** 能表來選取所需的叢集數。

   ![](assets/build_cluster_2.png)

1. 如果您想在資料集中叢集訪客的子集，可以定義人口篩選。

   ![](assets/build_cluster_3.png)

   首先，請使用工作區中的選取項目或使用來定義所需子集 **[!UICONTROL Filter Editor]**。 在您選取所需子集後，在功能表中設定「目標人口 **[!UICONTROL Options]** 族群」。 建議您為目標群組指定識別名稱。

   菜 **[!UICONTROL Options]** 單還具有控制最大刀路數和中心收斂的可接受閾值的設定。

1. 設定輸入和選項後，按一下「 **Go** 」按鈕，在本機執行叢集，或 **[!UICONTROL Submit]** 按以傳送工作至Predictive Analytics伺服器。 當收斂完成時，提交至伺服器會將產生的維度儲存至資料集。

   在本地運行時，您將看到Cluster Builder在四個樹冠叢集階段中移動，因為它根據輸入定義智慧中心。

   當群集的中心不再變化超過指定的收斂閾值時，群集維會收斂，而群集生成器會顯示有關輸入與每個群集的相關性的附加資訊。

1. 自訂叢集。

   在統計資料的色彩列上按一下滑鼠右鍵，可開啟內容選單，讓您自訂相關性臨界值，在維度元素分佈的情況下，選擇顯示的測試。

   ![](assets/build_cluster_7.png)

   度量輸入為每個群集提供t測試，而維度元素輸入則為每個群集提供三個分佈測試（Chi²、熵U統計值和Cramer的V統計值）。

   >[!NOTE]
   >
   >如果您在收斂期間新增或移除輸入，程式會暫停，直到您再次按 **Go** 。

   建立叢集後，您可以開啟檢色器，為不同的分佈結果指定顏色。

   ![](assets/build_cluster_5.png)

1. 在「叢集維度」聚合後，您可以新增量度至表格，並正常選取。 您也可以按一下右鍵元素名稱（群集1、群集2等）以開啟上下文菜單，將其更名為更有意義的內容。

   ![](assets/build_cluster_6.png)

1. 如果您想在其他視覺化中使用此叢集維度，您可以在本機 **[!UICONTROL Save]** 使用或將 **[!UICONTROL Submit]** 其用於伺服器。

如果您想要再次運行收斂或查看輸入的相關性，Cluster Builder也可以載入現有的群集維。

>[!TIP]
>
>選取後， **[!UICONTROL Reset]** 將完全釋放所有輸入變數，並提供空白的叢集建立器視覺化來定義新叢集。

