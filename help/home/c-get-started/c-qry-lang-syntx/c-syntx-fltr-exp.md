---
description: 篩選器是定義資料集中資料子集的運算式。
solution: Analytics
title: 篩選運算式的語法
topic: Data workbench
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 篩選運算式的語法{#syntax-for-filter-expressions}

篩選器是定義資料集中資料子集的運算式。

篩選器會根據維度間的關係，接納或拒絕每個維度的每個元素。

您可使用編輯篩選器 [!DNL Filter Editor]。 請參閱 [篩選編輯器](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3)。

在下表中，每個語法說明都包含使用該篩選的量度運算式範例。 例如，[SessionsTrue] 是使用「True」篩選器定義的量度。 SessionsTrue[] 量度與「工作階段」量度相同，因為「真」篩選器會接納「工作階段」維度的每個元素。

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>常數篩選。 承認每個維度的每個元素 </p> <p>範例：會話[ True ]與會話相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>常數篩選。 拒絕每個維度的每個元素。 </p> <p>範例：會話[ False ]始終為零。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不篩選 </p> </td> 
   <td colname="col2"> <p>承認篩選拒絕的元素。 </p> <p>範例：Sessions[ not Page="A" ]是未瀏覽頁面A的Sessions數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA和FilterB </p> </td> 
   <td colname="col2"> <p>承認FilterA和FilterB所承認的元素。 </p> <p>範例：會話數[ Page="A"和Page="B" ]是訪問頁面A和頁面B的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA或FilterB </p> </td> 
   <td colname="col2"> <p>承認FilterA或FilterB承認的元素。 </p> <p>範例：Sessions[ Page="A"或Page="B" ]是瀏覽頁面A、頁面B或兩者的作業數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>依尺寸篩選 </p> </td> 
   <td colname="col2"> <p>承認由「篩選器」(Filter)所允許的維度Dim的元素集。 </p> <p>範例：Sessions[ Page="/home" by Visitor ]是屬於瀏覽頁面"/home"的訪客的作業數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>識別碼 </p> </td> 
   <td colname="col2"> <p>參照篩選器在描述檔中另有定義。 </p> <p>範例：會話[ Broken_Session_Filter ]是「 Broken_Session Filter 」（中斷會話過濾器）所允許的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>承認尺寸Dim的給定元素。 </p> <p>範例：會話數[ Page="A" ]是訪問頁面A的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>尺寸&lt;&gt; "值" </p> <p>昏！= “值” </p> </td> 
   <td colname="col2"> <p>承認維度Dim的所有其他元素。 </p> <p>範例：會話數[頁面&lt;&gt;"A" ]是訪問A以外任何頁面的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 維= #序數 </td> 
   <td colname="col2"> <p>用給定的序數值承認維Dim的元素。 </p> <p>範例：Sessions[ Month=#0 ]是資料集第一個月中的Sessions數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>昏！= #Ordinal </p> </td> 
   <td colname="col2"> <p>承認維度Dim的所有其他元素。 </p> <p>範例：會話數[ Session_Value &lt;&gt; #0 ]是具有非零會話值的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim與"Expr"相符 </p> </td> 
   <td colname="col2"> <p>允許維度Dim的元素與給定的規則表達式匹配。 Dim不能是非正規或可計數的維度。 </p> <p>範例：會話[ URI與''匹配。*/產品/.*" ]是瀏覽產品目錄中任何頁面的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim notmatches "Expr" </p> </td> 
   <td colname="col2"> <p>承認維度Dim的元素與給定的規則表達式不匹配。 Dim不能是非正規或可計數的維度。 </p> <p>範例：會話[ URI不匹配''。*\.jsp" ]是訪問任何非JSP頁面的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>尺寸&lt; "值" </p> </td> 
   <td colname="col2"> <p>包含維Dim的元素，其序數值小於元素"Value"的序數值。如果"Value"不是維的元素，則假定它大於維的任何當前元素。 </p> <p>範例：會話數[月&lt; "04年7月" ]是2004年7月之前發生的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「尺寸&gt;值」 </p> </td> 
   <td colname="col2"> <p>包含維Dim的元素，其序數值大於元素"Value"的序數值。如果"Value"不是維的元素，則假定它大於維的任何當前元素。 </p> <p>範例：會話數[月&gt; "2004年7月" ]是2004年7月之後發生的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>尺寸&lt;= "值" </p> </td> 
   <td colname="col2"> <p>允許維Dim的元素，其序數值小於或等於元素"Value"的序數值。如果"Value"不是維的元素，則假定它大於維的任何當前元素。 </p> <p>範例：Sessions[ Session_Number &lt;= "2" ]是作為訪客第一個或第二個會話的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 尺寸&gt;= "值" </td> 
   <td colname="col2"> <p>包含維Dim的元素，其序數值大於或等於元素"Value"的序數值。如果"Value"不是維的元素，則假定它大於維的任何當前元素。 </p> <p>範例：Sessions[ Session_Number &gt;= "5" ]是訪客的第五個或更多作業的作業數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>任何尺寸 </p> </td> 
   <td colname="col2"> <p>承認尺寸Dim的所有元素。 </p> <p>範例：會話[任何Page_View ]是至少具有一個頁面視圖的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>無暗 </p> </td> 
   <td colname="col2"> <p>承認任何「尺寸」拒絕的元素。 </p> <p>範例：會話數[無Page_View ]是沒有頁面視圖的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>（篩選） </p> </td> 
   <td colname="col2"> <p>與FILTER相同；用於對過濾器表達式的一部分進行分組。 </p> </td> 
  </tr> 
 </tbody> 
</table>

