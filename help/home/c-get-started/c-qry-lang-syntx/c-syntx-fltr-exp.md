---
description: 篩選器是定義資料集中資料子集的運算式。
title: 篩選器運算式的語法
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# 篩選器運算式的語法{#syntax-for-filter-expressions}

{{eol}}

篩選器是定義資料集中資料子集的運算式。

篩選器會根據維度間的關係，承認或拒絕每個維度的每個元素。

您可以使用 [!DNL Filter Editor]. 請參閱 [篩選器編輯器](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

在下表中，每個語法說明都包含使用該篩選器的量度運算式範例。 例如工作階段[True] 是使用「True」篩選器定義的量度。 會議[True] 量度與「工作階段」量度相同，因為「真」篩選器會接納「工作階段」維度的每個元素。

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>常數篩選。 承認每個維度的每個元素 </p> <p>範例：會話[ True ]與會話相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>常數篩選。 拒絕每個維度的每個元素。 </p> <p>範例：工作階段[ False ]一律為零。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不篩選 </p> </td> 
   <td colname="col2"> <p>承認篩選拒絕的元素。 </p> <p>範例：Sessions[ not Page="A" ]是未造訪頁面A的Sessions數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA和FilterB </p> </td> 
   <td colname="col2"> <p>承認FilterA和FilterB承認的元素。 </p> <p>範例：Sessions[ Page="A"和Page="B" ]是同時瀏覽頁面A和頁面B的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA或FilterB </p> </td> 
   <td colname="col2"> <p>承認FilterA或FilterB承認的元素。 </p> <p>範例：Sessions[ Page="A"或Page="B" ]是瀏覽頁面A、頁面B或兩者的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>依維度篩選 </p> </td> 
   <td colname="col2"> <p>承認「篩選」所允許的維度「維度」的元素集。 </p> <p>範例：Sessions[ Page="/home" by Visitor ]是屬於瀏覽了頁面"/home"的訪客的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>識別碼 </p> </td> 
   <td colname="col2"> <p>引用篩選器，否則在配置檔案中定義。 </p> <p>範例：Sessions[ Broken_Session_Filter ]是「中斷的會話」篩選器所允許的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Value" </p> </td> 
   <td colname="col2"> <p>承認維度「維度」的指定元素。 </p> <p>範例：Sessions[ Page="A" ]是瀏覽頁面A的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>尺寸&lt;&gt; "值" </p> <p>暗！= “值” </p> </td> 
   <td colname="col2"> <p>承認維度「維度」的所有其他元素。 </p> <p>範例：Sessions[ Page&lt;&gt;"A" ]是瀏覽A以外任何頁面的Sessions數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 維度= #Ordinal </td> 
   <td colname="col2"> <p>使用給定的序數值承認維Dim的元素。 </p> <p>範例：Sessions[ Month=#0 ]是資料集第一個月的「工作階段」數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>維&lt;&gt; #Ordinal </p> <p>暗！= #序數 </p> </td> 
   <td colname="col2"> <p>承認維度「維度」的所有其他元素。 </p> <p>範例：Sessions[ Session_Value &lt;&gt; #0 ]是具有非零會話值的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim匹配「Expr」 </p> </td> 
   <td colname="col2"> <p>承認與指定規則運算式相符的維度「維度」的元素。 維度不得為非正規或可數維度。 </p> <p>範例：會話[ URI與「」匹配。*/product/.*" ]是訪問產品目錄中任何頁面的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim not與「Expr」匹配 </p> </td> 
   <td colname="col2"> <p>承認維度Dim的元素與指定的規則運算式不匹配。 維度不得為非正規或可數維度。 </p> <p>範例：會話[ URI不匹配「。*\.jsp" ]是訪問任何非JSP頁的頁的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>尺寸&lt; "值" </p> </td> 
   <td colname="col2"> <p>允許序數值小於元素「Value」的序數值的維Dim的元素。 如果「值」不是維度的元素，則會假設其大於維度的任何目前元素。 </p> <p>範例：Sessions[ Month &lt; "04" ]是2004年7月之前發生的Sessions數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>「維」&gt;「值」 </p> </td> 
   <td colname="col2"> <p>允許具有大於元素「Value」的序數值的序數值的維Dim的元素。 如果「值」不是維度的元素，則會假設其大於維度的任何目前元素。 </p> <p>範例：Sessions[ Month &gt; "Jul '04" ]是2004年7月之後舉行的Sessions數目。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>允許序數值小於或等於元素「Value」的序數值的維度Dim的元素。 如果「值」不是維度的元素，則會假設其大於維度的任何目前元素。 </p> <p>範例：Sessions[ Session_Number &lt;= "2" ]是訪客的第一或第二個工作階段的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>允許序數值大於或等於元素「值」的序數值的維度「維」的元素。 如果「值」不是維度的元素，則會假設其大於維度的任何目前元素。 </p> <p>範例：Sessions[ Session_Number &gt;= "5" ]是訪客的第五個或更多個工作階段的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>任何維度 </p> </td> 
   <td colname="col2"> <p>允許尺寸「尺寸」的所有元素。 </p> <p>範例：Sessions[ any Page_View ]是至少具有一個頁面檢視的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>無Dim </p> </td> 
   <td colname="col2"> <p>承認任何「維度」拒絕的元素。 </p> <p>範例：Sessions[ no Page_View ]是沒有頁面檢視的工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>（篩選） </p> </td> 
   <td colname="col2"> <p>與FILTER相同；用於將篩選器運算式的一部分分組。 </p> </td> 
  </tr> 
 </tbody> 
</table>
