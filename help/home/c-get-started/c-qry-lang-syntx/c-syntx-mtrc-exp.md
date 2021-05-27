---
description: 量度可使用量度編輯器來編輯，並儲存在設定檔的量度目錄中。
title: 量度運算式的語法
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
exl-id: 27d86fea-6500-4608-aadb-f39058fd3a6e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# 量度運算式的語法{#syntax-for-metric-expressions}

量度可使用量度編輯器來編輯，並儲存在設定檔的量度目錄中。

如需詳細資訊，請參閱[建立和編輯衍生量度](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40)。 量度運算式也可用於工作表中。 有關詳細資訊，請參閱[工作表](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581)。 下列語法可用來定義量度運算式。

附註:

1. 文字上應輸入帶底線的字詞。
1. 表單`{TEXT}?`代表選用文字。
1. 表單`{TEXT}*`表示可能發生零次或多次的文本。
1. 表單`{A | B | C |...}`表示只包含一個給定選項（如A、B或C...）的文本。.
1. 表單`[A,B)`表示從A到但不包括B的數字範圍。

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>識別碼 </p> </td> 
   <td colname="col2"> <p>識別碼會參考已命名的量度。 有關法律標識符的規則，請參見<a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8">標識符的語法</a>。 </p> <p>範例：收入= Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(量度) </p> </td> 
   <td colname="col2"> <p>（量度）的結果與量度的結果相同。 括弧指定運算式中的操作順序。 </p> <p>範例：平均=(A + B)/ 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>量度A和量度B的結果總和。 </p> <p>範例：值=收入+ Cost_Savings </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>量度A和量度B結果的差異。 </p> <p>範例：利潤=收入 — 成本 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>量度A和量度B結果的產品。 </p> <p>範例：美元=美分* 0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>量度A和量度B結果的比率。 </p> <p>範例：Revenue_per_Session = Revenue / Sessions </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A^ B </p> </td> 
   <td colname="col2"> <p>量度A的結果提升為量度B的結果的冪。 </p> <p>範例：區域=寬度^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>信賴度（量度） </p> </td> 
   <td colname="col2"> <p>量度標準差的預估值。 這是使用稱為折刀的取樣技術來計算。 </p> <p>此量度耗用大量記憶體，不應用於大型表。 </p> <p>若要使用此語法，您必須具有具有適當屬性的長刀尺寸（名為「長刀」）。 如需詳細資訊，請連絡Adobe諮詢服務。 </p> <p>範例：consity(Average_Score) </p> <p> <p>注意： 信賴度量類型(包括信賴度（量度）和信賴度（量度、jacknife），在使用Adobe的受控實驗功能時特別有用。 如果受控實驗期間量度從12%跳至16%，您可以使用信賴圖說來計算該跳至因隨機變異而產生的機率。 這可以幫助你避免從有限的證據中得出錯誤的結論，反之，還可以保證有問題的變化實際上是真實的。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>信賴度（量度，刺刀） </p> </td> 
   <td colname="col2"> <p>量度標準差的預估值。 這是使用稱為折刀的取樣技術來計算。 此語法可讓您使用名為「Jackknife」以外之名稱的Jackknife維度，來判斷量度的可信度。 </p> <p>此量度耗用大量記憶體，不應用於大型表。 </p> <p>若要使用此語法，您必須具有具有適當屬性的Jackknife尺寸（名為「Jackknife」以外的名稱）。 如需詳細資訊，請連絡Adobe諮詢服務。 </p> <p>範例：cursitence(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>將您參考的儲存格內容視為量度運算式。 此語法只能用於工作表視覺效果中。 </p> <p>範例：eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日誌(B、X) </p> </td> 
   <td colname="col2"> <p>數學對數函式：量度X為參數，量度B為基礎。 </p> <p>範例：dB = 20*log（幅度，10） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>量度[篩選] </p> </td> 
   <td colname="col2"> <p>「篩選的量度」：依指定篩選條件篩選的新量度。 </p> <p>範例：Jan_Sessions = Sessions[ Month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>依Dimension的量度 </p> </td> 
   <td colname="col2"> <p>在維度的「層級」評估的量度。 （M乘X）[F]的結果（用篩選器「F」評估的量度「M乘X」的結果）是M[F乘X]的結果（用篩選器「F乘X」評估的量度「M」的結果）。 </p> <p>範例：AB_Visitors = </p> <p>（依工作階段的訪客）[Page="A"和Page="B"] = </p> <p>依工作階段的訪客[（Page="A"和Page="B"）] = </p> <p>在同一工作階段中瀏覽頁面A和頁面B的訪客數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>數字 </p> </td> 
   <td colname="col2"> <p>具有固定值的量度。 </p> <p>範例：Pi = 3.1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(metric) </p> </td> 
   <td colname="col2"> <p>忽略評估量度的任何維度。 該維度的每個元素的量度都有相同的值。 </p> <p>範例：Pct_of_Visitors =訪客/總計（訪客） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all（量度） </p> </td> 
   <td colname="col2"> <p>忽略套用至量度的篩選器。 量度不受選取項目和其他篩選器影響。 </p> <p>範例：Benchmark_Sessions = all(Sessions) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(metric)) </p> </td> 
   <td colname="col2"> <p>忽略所有篩選器和維。 無論套用的篩選器或維度為何，其值在整個指定設定檔中都會相同。 </p> <p>範例：Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>提供可數維度（例如「訪客」或「工作階段」）的計數的量度。 </p> <p>範例：訪客= sum(One,Visitor) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(數值_Dimension，可數_Dimension) </p> </td> 
   <td colname="col2"> <p>在可數維度上提供數值維度總和的量度。 會使用數值維元素的序數值（與格式化值相反），因此通常需要對結果應用比例因子。 </p> <p>範例：值= sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>量度A和量度B的結果較小。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>量度A和量度B的結果中的較大者。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>格式(A、B) </p> </td> 
   <td colname="col2"> <p>與量度A相同的量度，但使用量度B的格式功能。 </p> </td> 
  </tr> 
 </tbody> 
</table>
