---
description: 模型檢視器可讓您使用「傾向評分」功能產生Logistic回歸模型。
solution: Analytics
title: 模型檢視器
topic: Data workbench
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Model Viewer{#model-viewer}

模型檢視器可讓您使用「傾向評分」功能產生Logistic回歸模型。

模型檢視器會顯示每個輸入變數的系數權重（包括常數項目）及其統計誤差範圍。 模型中，絕對系數高、誤差裕度小的輸入變數是最重要的預測器。

**要開啟模型查看器圖表**

1. 選擇 [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. 將滑鼠指標暫留在已儲存分數的「模型完成」上。

![](assets/propensity_model_viewer.png)

系數>=1的輸入變數對傾向模型有正面影響。 小於1的系數對傾向模型有負影響。 括弧中定義的範圍是錯誤，並指出輸入變數在成功人口族群中的一致性。