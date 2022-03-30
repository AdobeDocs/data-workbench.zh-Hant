---
description: 在運行實驗直至所需的最小訪問者數量參與實驗後，可以確保有足夠的統計置信度來評估實驗的結果。
solution: Analytics
title: 評估實驗
uuid: 88fd81bc-b944-48ea-bd4d-8716979ec69e
exl-id: 5add2168-f6bc-45c5-bf1d-1191a38c5bac
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# 評估實驗{#evaluating-the-experiment}

在運行實驗直至所需的最小訪問者數量參與實驗後，可以確保有足夠的統計置信度來評估實驗的結果。

使用 [!DNL Insight]，比較作為假設的一部分定義的指標或關鍵績效指標以確定該實驗是否成功（即，該假設在指定置信度下被驗證）。

在實例實驗中，如果訪客轉換率至少提高1.5%，那麼我們的假設是正確的，這是我們先前定義的成功准則。

下面的工作區示例顯示，index2test組的Conversion實際上比控制組高1.8%，這證明了我們的假設。

![](assets/experimentresults.png)

* [總結實驗結果](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-24a496c080a04e929764094acb00bab7)
* [基於結果採取行動](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1623e26ced524fd9beab48ac1f9165d9)
* [監視您的操作](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1954311950c34637800cbd7c0711983f)

## 總結實驗結果 {#section-24a496c080a04e929764094acb00bab7}

使用 [!DNL Insight]，可以建立詳細報告來總結和說明實驗的結果。

然後，您可以使用報告（如下例所示）根據結果提出建議，這些結果由您在報告中提供的可視資訊備份：

![](assets/experimentresults2.png)

## 基於結果採取行動 {#section-1623e26ced524fd9beab48ac1f9165d9}

在結果清楚後，您就可以對這些結果採取行動，方法是：對測試的頁面進行生產級更改，將這些更改應用到網站的其他區域，並確保完整記錄test、結果和您所做的更改。

## 監視您的操作 {#section-1954311950c34637800cbd7c0711983f}

在控制實驗完成並實施了相應更改後，請確保繼續監視通過以下方式所做的更改：查看驗證度量、建立控製圖表和提供儀表板度量。

如果您認為測試和所做的更改沒有影響原始結果，請務必準備重新test您的假設。
