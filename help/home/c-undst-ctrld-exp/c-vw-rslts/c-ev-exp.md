---
description: 在執行實驗直到需要的最小訪客數量參與實驗為止之後，您就可以確保有足夠的統計信賴度來評估實驗的結果。
solution: Analytics,Analytics
title: 評估實驗
uuid: 88fd81bc-b944-48ea-bd4d-8716979ec69e
exl-id: 5add2168-f6bc-45c5-bf1d-1191a38c5bac
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# 評估實驗{#evaluating-the-experiment}

在執行實驗直到需要的最小訪客數量參與實驗為止之後，您就可以確保有足夠的統計信賴度來評估實驗的結果。

使用[!DNL Insight]，比較定義為假設一部分的量度或關鍵績效指標，以判斷實驗是否成功（亦即，假設已以指定信賴度驗證）。

在我們的範例實驗中，如果訪客轉換至少增加1.5%，即為我們先前定義的成功標準，我們的假設即已證實正確。

以下工作區範例顯示index2測試群組的轉換實際上較控制群組高1.8%，證明了我們的假設。

![](assets/experimentresults.png)

* [總結實驗結果](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-24a496c080a04e929764094acb00bab7)
* [根據結果採取行動](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1623e26ced524fd9beab48ac1f9165d9)
* [監控動作](../../../home/c-undst-ctrld-exp/c-vw-rslts/c-ev-exp.md#section-1954311950c34637800cbd7c0711983f)

## 總結實驗結果{#section-24a496c080a04e929764094acb00bab7}

使用[!DNL Insight]，您可以建立詳細報告來匯總並說明實驗的結果。

然後，您可以使用您的報表（如下列範例所示），根據結果提出建議，而結果會以您在報表中提供的視覺資訊作為備份：

![](assets/experimentresults2.png)

## 根據結果{#section-1623e26ced524fd9beab48ac1f9165d9}採取行動

結果清楚後，您就可以對測試頁面進行生產層級的變更，將相同的變更套用至網站的其他區域，並確實完整記錄測試、測試結果和您所做的變更，借此對這些結果採取行動。

## 監控您的動作{#section-1954311950c34637800cbd7c0711983f}

受控實驗完成並實施了適當的更改後，請務必繼續監視您通過（例如，查看驗證度量、建立控製圖表和提供控制面板度量）所做的更改。

如果您認為測試和所做的變更未影響原始結果，請務必準備好重新測試您的假設。
