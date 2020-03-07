---
description: 信賴圖例可協助您判斷您看到的數字是偶然發生的可能性，並瞭解資料中可能的偏差。
solution: Analytics
title: 信賴圖例
topic: Data workbench
uuid: 2559ff7c-6060-4fee-b509-9ae0c3912016
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 信賴圖例{#confidence-legends}

信賴圖例可協助您判斷您看到的數字是偶然發生的可能性，並瞭解資料中可能的偏差。

即使您不是取樣資料，也無法完全信賴地從特定時段或子集推斷數字至其他時段或子集。 信賴圖例可讓您探索數字落在特定範圍內的可能性。

如果你認為現實世界的資料是一個重大實驗，那麼現實世界仍然有機會，即使用精確的數字。 例如，知道在某個星期二上午8點到下午12點之間完成交易的人數並不意味著在下週二完成交易的人數完全相同。

下列信賴圖例會顯示「轉換」度量的信賴詳細資訊，而下表則提供每個資料點的詳細資訊。

![](assets/lgd_ConfidenceLegend.png)

<table id="table_387F22C7EF4E4DE9AD810D3D9204676F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>量度或公式 </p> </td> 
   <td colname="col2"> <p>您要檢視信賴資訊的量度名稱或量度運算式。 您在工作區中所做的任何選擇都會反映在圖例中。 此範例顯示「轉換」度量的詳細資訊。 </p> <p>有關輸入表達式的語法規則的資訊，請參 <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f"> 閱查詢語法</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>測量值 </p> </td> 
   <td colname="col2"> <p>收集的實際資料值。 在此範例中，目前選擇的轉換率為2.3%。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準差 </p> </td> 
   <td colname="col2"> <p>測量值的標準差。 在此範例中，目前選擇的轉換率標準偏差為0.1%。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>"true"值 </p> </td> 
   <td colname="col2"> <p>「測量值」落在每個概率所列範圍內的可能性。 在此範例中，如果一再重複此「實際實驗」，您可以90%確定「測量值」在2.1%到2.4%之間。 </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>在分析任何計算結果時，必須考慮以下注意事項：>
>* 這些數字是估算。 如果您使用不同的資料集重複相同的計算，則會得到不同的結果。 這稱為隨機變化。
>* 對概率較高的推斷取決於對所有指標來說都不正確的正態假設。 因此，99%概率的值比90%概率的值更不可靠。
>
>
如果您需要更精確的數字，請咨詢統計專家。

## 變更量度或公式 {#section-7f09ff84c3514f26b78d29294e1f03d9}

* 在信賴圖例中，按一下欄位 **[!UICONTROL Metric or Formula]** 並輸入所要的量度或運算式。 如需運算式語法規則，請參 [閱查詢語言語法](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)。

## 匯出至Microsoft Excel {#section-f36e2db7273740b7af278f8a2b79d564}

有關導出窗口的資訊，請參 [閱導出窗口資料](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)。
