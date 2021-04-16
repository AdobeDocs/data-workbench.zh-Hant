---
description: 註解是您新增至工作區的視窗，可建立包含該元素虛擬選取範圍的新視覺化，以吸引特定維度元素的注意。
title: 為工作區新增圖說文字
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
exl-id: fcdb9231-d44a-4287-b799-6a66f7f79432
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 2%

---

# 為工作區新增圖說文字{#adding-callouts-to-a-workspace}

註解是您新增至工作區的視窗，可建立包含該元素虛擬選取範圍的新視覺化，以吸引特定維度元素的注意。

Data Workbench以標準的註解類型集提供。 由於您的實作可以完全自訂，因此您實作中顯示的可用註解類型可能與本指南中記載的內容不同。

依預設，Data Workbench提供下列圖說：

* [注釋](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [空白線圖](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [空白散布圖](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [空白表格](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [信賴圖例](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [量度圖例](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>圖說不能當做選取範圍（也就是說，它們不會影響工作區中的其他視覺化），除非您在圖說中進行選取。

通過配置儲存在&#x200B;*配置檔案名*\Context\Callout folder of the [!DNL Server]安裝資料夾中的註解檔案，可以添加或編輯註解定義。 請參閱[配置註解](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a)。

## 要向可視化添加註釋註解{#section-7b6742160b3f4aed872a09c8c023f90d}

1. 按一下右鍵要為其建立註解的元素，然後按一下&#x200B;**[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]**&#x200B;或&#x200B;**[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**。 會顯示空白視窗，其中顯示該元素的可見連線。

   ![](assets/client-call.png)

   若要將圖說新增至圖形視覺化，您必須在視覺化（基軸）底部按一下滑鼠右鍵，以開啟功能表。

   ![](assets/visualization_callout_linegraph.png)

1. 視您的選擇而定，請完成適當的步驟：

   * 對於文本批注，請鍵入或將所需文本貼上到註解中，然後根據需要設定文本格式。 請參閱[使用文本注釋](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)。
   * 對於影像批注，通過複製影像，然後在註解內按一下右鍵，將所需影像貼上到註解中。 按一下「**[!UICONTROL Paste image]**」。請參閱[使用影像註解](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962)。

## 要將空白表格、折線圖或散布圖註解新增至視覺化{#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. 按一下右鍵要為其建立註解的元素，然後按一下&#x200B;**[!UICONTROL Add Callout]** > ***[!UICONTROL callout type]**>*。

   以下示例顯示「空表」(Blank Table)註解。

   ![](assets/vis_callout_blank_bar_graph.png)

1. 要選擇維，請按一下右鍵&#x200B;**[!UICONTROL None]** ，然後按一下&#x200B;**[!UICONTROL Change Dimension]** > ***[!UICONTROL dimension name]**>*。

   >[!NOTE]
   >
   >如果在具有註解的可視化中更改尺寸，註解將從連接到原始尺寸的元素變為連接到整個可視化。

## 若要將信賴圖例註解新增至視覺化{#section-386d1293ddc24a0c9cccb332e20db791}

1. 按一下右鍵要為其建立註解的元素，然後按一下&#x200B;**[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**。

   ![](assets/vis_callout_confidenceLegend.png)

1. 視需要變更[!DNL Metric or Formula]欄位。

如需運算式語法規則，請參閱[查詢語言語法](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。 請參閱[信賴圖例](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd)。

## 若要將量度圖例圖說圖說新增至視覺化{#section-daa6d372c22246d9827880a9d6e804d8}

1. 按一下右鍵要為其建立註解的元素，然後按一下&#x200B;**[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**。

   ![](assets/vis_callout_metricLegend.png)

1. 視需要，新增量度至量度圖例或移除量度。

請參閱[量度圖例](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)。
