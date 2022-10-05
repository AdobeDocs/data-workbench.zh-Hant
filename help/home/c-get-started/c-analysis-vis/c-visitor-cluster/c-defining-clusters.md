---
description: 選取輸入變數、叢集數目和目標母體（如果需要），以定義資料集中的叢集。
title: 建立叢集
uuid: f8462445-b7d2-48ae-aed7-2a3abc491cfb
exl-id: 60bc75bf-2f89-455b-8be9-aa20bb837752
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 1%

---

# 建立叢集{#building-clusters}

{{eol}}

選取輸入變數、叢集數目和目標母體（如果需要），以定義資料集中的叢集。

**建立叢集**

1. 開啟 **[!UICONTROL Cluster Builder]**.

   按一下 **視覺效果** > **預測性分析** > **聚類** > **叢集產生器**.

   ![](assets/cluster-builder-step1.png)

1. 選取輸入變數。

   * 新增量度至 **[!UICONTROL Input Variables]** 清單，從 **[!UICONTROL Metric]** 的雙曲餘切值。

      ![](assets/cluster_metric_select.png)

   * 新增維度元素至 **[!UICONTROL Input Variables]** 清單，從Dimension的表格中拖曳。

      Press **[!UICONTROL Ctrl + Alt]** 和拖動選定的維元素至 **[!UICONTROL Input Variables]** 清單或 **[!UICONTROL Element]** 框中，選擇該選項。

      ![](assets/cluster_dim_select.png)
   依預設，會對整個資料集執行叢集。 您可以在左側看到所有輸入變數 **[!UICONTROL Preprocessing]** 框。
1. 使用 **[!UICONTROL Options]** 選項，選擇所需的群集數。

   ![](assets/build_cluster_2.png)

1. 如果您想在資料集中叢集訪客的子集，可以定義母體篩選。

   ![](assets/build_cluster_3.png)

   首先，使用工作區中的選取項目或使用 **[!UICONTROL Filter Editor]**. 選取所需的子集後，在 **[!UICONTROL Options]** 功能表。 建議您為目標群組指定識別名稱。

   此 **[!UICONTROL Options]** 菜單還具有控制最大刀路數和中心收斂的可接受閾值的設定。

1. 設定輸入和選項後，按一下 **開始** 按鈕在本地運行群集或按鍵 **[!UICONTROL Submit]** 將任務傳送至預測分析伺服器。 收斂完成時，提交至伺服器會將產生的維度儲存至資料集。

   在本地運行時，你會看到集群生成器在四個樹冠叢集階段中移動，它根據輸入定義智慧中心。

   當群集的中心停止更改超過指定的收斂閾值時，群集Dimension就會收斂，群集生成器將顯示有關輸入與每個群集的相關性的其他資訊。

1. 自訂叢集。

   按一下右鍵統計資訊的顏色欄會開啟一個上下文菜單，允許您自定義相關性閾值，在維元素分配的情況下，可以選擇顯示哪個測試。

   ![](assets/build_cluster_7.png)

   度量輸入為每個簇提供一個t檢驗，而維元素輸入為每個簇提供三個分佈測試（Chi平方、熵U統計和Cramer V統計）。

   >[!NOTE]
   >
   >如果在收斂期間添加或刪除輸入，則進程將暫停，直到您按下 **開始** 。

   建立叢集後，您可以開啟檢色器，為不同的分佈結果指派顏色。

   ![](assets/build_cluster_5.png)

1. 叢集Dimension聚合後，您可以將量度新增至表格，並正常進行選取。 您也可以以滑鼠右鍵按一下元素名稱（叢集1、叢集2等），開啟內容功能表，將其重新命名為更有意義的名稱。

   ![](assets/build_cluster_6.png)

1. 如果您想在其他視覺效果中使用此叢集維度，您可以 **[!UICONTROL Save]** 本機或 **[!UICONTROL Submit]** 到伺服器。

如果您想要再次運行收斂，或查看輸入的相關性，則群集生成器還可載入現有群集維。

>[!TIP]
>
>若選取， **[!UICONTROL Reset]** 會完全釋出所有輸入變數，並提供空白的叢集產生器視覺效果來定義新叢集。
