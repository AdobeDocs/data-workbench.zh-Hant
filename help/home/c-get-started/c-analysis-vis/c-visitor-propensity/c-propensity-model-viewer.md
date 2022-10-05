---
description: 模型檢視器可讓您使用「傾向分數」功能產生Logistic回歸模型。
title: 模型檢視器
uuid: 7ee8ff29-21c2-4721-804a-c7a5d101b50b
exl-id: e0e4acd4-76a2-436a-993b-2bb7ca91ae1a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 3%

---

# 模型檢視器{#model-viewer}

{{eol}}

模型檢視器可讓您使用「傾向分數」功能產生Logistic回歸模型。

模型檢視器會顯示每個輸入變數的系數加權（包括常數項）及其統計誤差範圍。 顯示高絕對系數和小誤差裕度的輸入變數是模型中最重要的預測器。

**要開啟模型查看器圖表**

1. 選擇 [!DNL Add Visualization > Predictive Analytics > Scoring] .
1. 暫留在已儲存分數的「模型完成」上。

![](assets/propensity_model_viewer.png)

系數>=1的輸入變數對傾向模型有正面影響。 小於1的系數對傾向模型有負影響。 括弧內定義的範圍是錯誤，並指出輸入變數在成功母體中的一致性。
