---
description: 傾向分數可讓您根據客戶成功轉換或完成指定事件的可能性來定義客戶。 它可讓您在執行程式或引導促銷活動之前，將工作的潛在影響最大化。
solution: Analytics
title: 傾向得分
topic: Data workbench
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 傾向得分{#propensity-scoring}

傾向分數可讓您根據客戶成功轉換或完成指定事件的可能性來定義客戶。 它可讓您在執行程式或引導促銷活動之前，將工作的潛在影響最大化。

## 傾向得分的值 {#section-c51ece66effc42de9b754f0f46027c1b}

傾向分數可讓您執行資料發現，以識別資料中隱藏的行為或模式。 具體而言，傾向得分有助於使用更具焦點和目標的方式 (而不是簡單的劃分或篩選) 來識別一組類似客戶。此外，傾向得分可讓您設定預測性功能，以識別公司的高價值客戶的行為。

一旦識別出高價值受眾，您可以開發他們以獲得最好的效果。例如，如果您是「企業對企業」公司，您可能會有銷售電話銷售線索，這可讓您對銷售線索評分並識別其離線轉換的可能性。 因為每個銷售機會均會增加成本，建立獎勵來識別具有的轉換銷售可能性最高的預期客戶最為有效，並且是集中資源成本最低的方式。

傾向得分提供識別這些因素中特定得分最具預測性，或是增加事件發生可能性的功能，但也可以套用來回答特定問題: 客戶是否將進行轉換? 客戶是否將回應電子郵件? 客戶是否將重新購買? 傾向得分可讓您回答這些問題，並利用之後可設定和計分的動作傾向來識別訪客。

此外，您也可以使用篩選條件來定義要使用選用功能的訪客子 **[!UICONTROL Training Filter]** 集。 如果未套用篩選，則所有訪客都會定位以進行計分。

## 傾向得分視覺化的功能 {#section-28413bc7d33b42c59cecb427c1c5a3fa}

若要開啟「傾向分數視覺化」，請按一 **[!UICONTROL Add]** 下> **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**。

![](assets/propensity_visualization_GO.png)

「傾向分數視覺化」包含可從工具列存取的下列功能：

| 工具列功能 | 說明 |
|---|---|
| 前往 | 在設定參數後，按一下以執行計分程式。 |
| 重設 | 清除視覺化中的所有設定。 |
| 載入 | 載入先前建立的ScoreDim，可讓您變更及／或重建計分模型。 |
| 儲存 | 將「傾向分數」視覺化儲存為Dim檔案，以視需要存取和開啟。 |
| 提交 | 提交計分工作以進行伺服器端處理。 |
| 選項 | 設定「訓練篩選」以限制訪客的子集。 預設篩選是 **[!UICONTROL Train on Everyone]**，但您可以透過選擇工作區或使用建立篩選來變更 **[!UICONTROL Filter Editor]**。 |
| 設定目標 | 設定從屬變數。 |
| 量度 | 新增量度為獨立變數。 |
| 元素 | 使用「維」表格中的 `<Ctrl>` + `<Alt>` 鍵拖動維元素。 |

**另請參閱**:

* 增益 [和提升度圖表](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a)。 這些檢視可從完整的計分模型或 [!DNL Add Visualization> Predictive Analytics > Scoring.]
* 模型 [檢視器](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd)。 這些檢視可從完整的計分模型或 [!DNL Add Visualization> Predictive Analytics > Scoring.]
* 「復 [雜篩選描述](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) 」功能。

## 使用傾向分數視覺化 {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **定義一或多個篩選條件，以定義要計分的訪客人數**。 此選項可 **[!UICONTROL Training Filter]** 讓您根據選取的條件來定位訪客。 如果未套用訓練篩選，則所有訪客都會定位以進行計分。 如果已設定「訓練篩選」，則計分結果會對已定義的訪客人數產生意義，不過仍會給每個訪客分數。
* **識別正面訪客**。 若要定義相依變數，以指定識別符合所需結果之正面訪客的目標篩選。 這可以像「收入> $10」或更複雜的篩選條件一樣簡單。
* **「目標」篩選條件不允許與「訓練」篩選條件相同**。 從邏輯上講，「目標篩選」應是「訓練篩選」的新增項目，以產生要計分的訪客人數正子集。
* **選取興趣變數（獨立變數）作為傾向評分演算法的輸入**。 這些可以是「量度」或維度的個別元素。 傾向分數會像訪客叢集一樣開始 [進行預處理](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d)。 系統開始擷取與先前設定之訓練篩選的定義相符的特定樣本量（如果有的話）。 目前，樣本大小設定為計分人口數的10%（由訓練篩選器定義），最少為20,000個，最多為100,000個，並系結至計分人口數大小。

* 「分數維度」的元素範圍從0%到100%，可決定訪客符合「目標」變數的可能性。

