---
description: 傾向分數可讓您根據客戶成功轉換或完成指定事件的可能性來定義客戶。 它可讓您在執行程式或引導行銷活動之前，盡可能發揮行銷活動的潛在影響。
title: 傾向分數
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 24%

---

# 傾向分數{#propensity-scoring}

{{eol}}

傾向分數可讓您根據客戶成功轉換或完成指定事件的可能性來定義客戶。 它可讓您在執行程式或引導行銷活動之前，盡可能發揮行銷活動的潛在影響。

## 傾向分數的價值 {#section-c51ece66effc42de9b754f0f46027c1b}

傾向分數可讓您執行資料探索，以識別資料中存在的隱藏行為或模式。 具體而言，傾向分數可協助您使用更聚焦且客觀的方式來識別類似客戶的叢集，而不是使用簡單的細分或篩選方式。此外，傾向分數可讓您建立預測能力，識別貴公司高價值客戶的行為。

一旦識別出高價值受眾，您就可以吸引他們參與以發揮最大效果。例如，如果您是企業對企業的公司，您可能有銷售電話銷售機會，允許您對銷售機會進行評分並確定其離線轉換的可能性。 由於每個銷售機會都會增加成本，因此建立獎勵來識別最有可能轉換銷售的潛在客戶，是集中資源最有效且成本最低的方式。

傾向分數可讓您識別最能預測特定分數，或增加發生事件之可能性的因素，但也可套用以回答特定問題：客戶是否會轉換？客戶是否會回覆電子郵件？客戶是否會回購？傾向分數可讓您回答這些問題，並識別有傾向採取動作的訪客，接著便可針對這些動作進行設定和評分。

此外，您也可以使用篩選條件，使用選用項目來定義要評分的訪客子集 **[!UICONTROL Training Filter]** 功能。 如果未套用篩選，則所有訪客都會定位以進行計分。

## 傾向分數視覺效果的功能 {#section-28413bc7d33b42c59cecb427c1c5a3fa}

若要開啟「傾向分數」視覺效果，請按一下 **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

「傾向分數」視覺效果包含可從工具列存取的下列功能：

| 工具列功能 | 說明 |
|---|---|
| 開始 | 在設定參數後，按一下以執行計分程式。 |
| 重設 | 清除視覺效果中的所有設定。 |
| 載入 | 載入先前建立的ScoreDim，可讓您變更和/或重建計分模型。 |
| 儲存 | 將「傾向分數」視覺效果儲存為「維度」檔案，以供視需要存取及開啟。 |
| 提交 | 提交計分任務以進行伺服器端處理。 |
| 選項 | 設定「訓練篩選器」以限制訪客的子集。 預設篩選條件為 **[!UICONTROL Train on Everyone]**，但您可以透過選取工作區或使用建立篩選器來變更 **[!UICONTROL Filter Editor]**. |
| 設定目標 | 設定相依變數。 |
| 量度 | 新增量度作為獨立變數。 |
| 元素 | 使用拖曳Dimension元素 `<Ctrl>` + `<Alt>` Dimension表的鍵。 |

**另請參閱**:

* 此 [增益和提升圖](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). 這些檢視可從完整計分模型或從 [!DNL Add Visualization> Predictive Analytics > Scoring.]
* 此 [模型查看器](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). 這些檢視可從完整計分模型或從 [!DNL Add Visualization> Predictive Analytics > Scoring.]
* 此 [複雜篩選器說明](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) 功能。

## 使用傾向分數視覺效果 {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **定義一或多個篩選器以定義要計分的訪客母體**. 此選填 **[!UICONTROL Training Filter]** 可讓您根據選取的條件來鎖定訪客。 如果未套用訓練篩選，則所有訪客都會定位以進行計分。 如果設定了訓練篩選，則分數結果對定義的訪客人口有意義，雖然仍會為每位訪客指定分數。
* **識別正面訪客**. 定義相依變數以指定目標篩選器，識別符合所需結果的正面訪客。 這可以簡單如「收入> $10」，或是更複雜的篩選條件。
* **Target篩選器不得與訓練篩選器相同**. 邏輯上，目標篩選器應是訓練篩選器的新增項目，因此需對訪客母體評分為正子集。
* **選取興趣變數（獨立變數）作為「傾向分數」演算法的輸入**. 這些可以是量度或Dimension的個別元素。 傾向分數會開始預處理，如 [訪客叢集](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). 系統開始捕獲與先前設定的訓練過濾器（如果有）的定義匹配的特定數量的樣本。 目前，樣本大小設定為計分母體的10%（由訓練篩選器定義），最小為20,000，最大為100,000，並且與計分母體大小相關。

* 「分數」Dimension的元素範圍介於0%到100%之間，可判斷訪客符合Target變數的可能性。
