---
description: 量度可使用量度編輯器編輯，並儲存在描述檔的量度目錄中。
title: 量度運算式的語法
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
exl-id: 27d86fea-6500-4608-aadb-f39058fd3a6e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---

# 量度運算式的語法{#syntax-for-metric-expressions}

量度可使用量度編輯器編輯，並儲存在描述檔的量度目錄中。

如需詳細資訊，請參閱[建立和編輯衍生量度](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40)。 量度運算式也可用於工作表中。 如需詳細資訊，請參閱[工作表](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581)。 以下語法用於定義量度運算式。

附註:

1. 在運算式文字中應輸入帶底線的字詞。
1. `{TEXT}?`表示可選文本。
1. `{TEXT}*`表示可能發生零次或多次的文字。
1. `{A | B | C |...}`表示由給定選項（如A或B或C）中的一個完全組成的文本。.
1. 表單`[A,B)`表示數字範圍，從A到但不包括B。

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>識別碼 </p> </td> 
   <td colname="col2"> <p>識別碼會參照命名的量度。 有關管理法律標識符的規則，請參見<a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8">標識符的語法</a>。 </p> <p>範例：收入= Total_Price </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(量度) </p> </td> 
   <td colname="col2"> <p>（量度）的結果與量度的結果相同。 括弧指定運算式中的運算順序。 </p> <p>範例：平均值=(A + B)/ 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>量度A和量度B的結果總和。 </p> <p>範例：值=收入+成本節省 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>量度A和量度B的結果差異。 </p> <p>範例：利潤=收入——成本 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>量度A和量度B結果的乘積。 </p> <p>範例：美元=美分* 0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A/B </p> </td> 
   <td colname="col2"> <p>量度A和量度B的結果比例。 </p> <p>範例：Revenue_per_Session = Revenue / Sessions </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>量度A的結果提升為量度B的結果的冪。 </p> <p>範例：面積=寬度^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>信賴（量度） </p> </td> 
   <td colname="col2"> <p>量度標準差的估計值。 這是使用稱為「折刀」的取樣技術計算的。 </p> <p>此量度耗用大量記憶體，不應用於大型表格。 </p> <p>若要使用此語法，您必須具有具有適當屬性的折刀尺寸（稱為「折刀」）。 如需詳細資訊，請聯絡Adobe諮詢服務。 </p> <p>範例：信賴（平均分數） </p> <p> <p>注意： 信賴度量類型，包括信賴度量（量度）和信賴度量（量度，傑克尼夫），在使用Adobe的受控實驗功能時特別有用。 如果量度在受控實驗期間從12%跳至16%，您可以使用信賴圖說來計算因隨機變化而跳躍的機率。 這可協助您避免從有限的證據中得出錯誤的結論，反之，也能保證可疑的變更是真實的。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>信賴度（量度，折刀） </p> </td> 
   <td colname="col2"> <p>量度標準差的估計值。 這是使用稱為「折刀」的取樣技術計算的。 此語法可讓您使用名為"jackknife"以外之名稱的Jackknife維度來判斷量度的可信度。 </p> <p>此量度耗用大量記憶體，不應用於大型表格。 </p> <p>若要使用此語法，您必須具有具有適當屬性的折刀尺寸（取名為"jackknife"以外的名稱）。 如需詳細資訊，請聯絡Adobe諮詢服務。 </p> <p>範例：信賴(Average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>將您參照的儲存格內容視為度量運算式。 此語法只能用於工作表視覺化。 </p> <p>範例：eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日誌(B、X) </p> </td> 
   <td colname="col2"> <p>數學對數函式：量度X是參數，量度B是基礎。 </p> <p>範例：dB=20*log（振幅，10） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>量度[篩選] </p> </td> 
   <td colname="col2"> <p>"篩選的量度":由指定篩選器篩選的新度量。 </p> <p>範例：Jan_Sessions =會話[ Month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>量度(依Dimension) </p> </td> 
   <td colname="col2"> <p>在維度的「層級」評估的量度。 (M by X)[F]（使用篩選器"F"評估的量度"M by X"的結果）的結果是M[F by X]（使用篩選器"F by X"評估的量度"M"的結果）的結果。 </p> <p>範例：AB_Visitors = </p> <p>（依工作階段的訪客）[Page="A"和Page="B"] = </p> <p>依工作階段的訪客[（Page="A"和Page="B"）] = </p> <p>在相同作業中瀏覽頁面A和頁面B的訪客數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>數字 </p> </td> 
   <td colname="col2"> <p>具有固定值的量度。 </p> <p>範例：Pi = 3.1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Metric) </p> </td> 
   <td colname="col2"> <p>忽略評估量度的任何維度。 量度對該維度的每個元素都有相同的值。 </p> <p>範例：Pct_of_Visitors =訪客／總計（訪客） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all（量度） </p> </td> 
   <td colname="col2"> <p>忽略套用至量度的篩選。 量度不受選取範圍和其他篩選條件的影響。 </p> <p>範例：Benchmark_Sessions = all(Sessions) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(all(metric)) </p> </td> 
   <td colname="col2"> <p>忽略所有篩選器和維度。 不論套用的篩選器或尺寸為何，它在指定的描述檔中都有相同的值。 </p> <p>範例：Dataset_Visitors = total(all(Visitors)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>提供可計數維度（例如「訪客」或「工作階段」）的計數的量度。 </p> <p>範例：訪客=sum（一位訪客） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_Dimension, Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>在可計數維度上提供數值維度總和的量度。 會使用數值維度元素的序數值（與格式化值相反），因此通常需要套用比例系數至結果。 </p> <p>範例：值= sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>量度A和量度B的較低結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>量度A和量度B的結果越大。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>格式(A、B) </p> </td> 
   <td colname="col2"> <p>與量度A相同的量度，但使用量度B的格式功能除外。 </p> </td> 
  </tr> 
 </tbody> 
</table>
