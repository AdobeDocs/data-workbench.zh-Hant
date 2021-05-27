---
description: Dimension運算式絕不能單獨使用，但可在量度或篩選器運算式中呼叫維度的任何位置使用。
title: 維度運算式的語法
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# 維度運算式的語法{#syntax-for-dimension-expressions}

Dimension運算式絕不能單獨使用，但可在量度或篩選器運算式中呼叫維度的任何位置使用。

1. 文字上應輸入帶底線的字詞。
1. 表單`{TEXT}?`代表選用文字。
1. 表單`{TEXT}*`表示可能發生零次或多次的文本。
1. 表單`{A | B | C |...}`表示只包含一個給定選項（如A、B或C...）的文本。.
1. 表單`[A,B)`表示從A到但不包括B的數字範圍。

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>識別碼 </p> </td> 
   <td colname="col2"> <p>標識符引用命名的維。 有關法律標識符的規則，請參見<a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8">標識符的語法</a>。 </p> <p>範例：Sessions[ Session_Number = "1" ]是會話數為"1"的會話數。 工作階段編號是識別碼參考的命名維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(維度) </p> </td> 
   <td colname="col2"> <p>(Dimension)的結果與Dimension的結果相同。 括弧指定運算式中的操作順序。 </p> <p>範例：Sessions[(Page)= "/home" ]是瀏覽頁面"/home"的Sessions數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>逐級變暗 </p> </td> 
   <td colname="col2"> <p>定義一個維，該維的元素與維「尺寸」相同，但通過維級別與其他維相關。 </p> <p>具體來說，新維的元素與級別的相同元素相關，並且與與級別的任何元素相關的任何其他維的這些元素相關。 </p> <p>範例：Sessions[(Page by Visitor)="/home" ]是造訪頁面"/home"的訪客工作階段數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>定義與尺寸尺寸尺寸具有相同元素的尺寸。 維級別的eth元素與新維的相同元素相關，而與級別的e+N元素相關的維的元素相關，前提是級別的eth和e+Nn元素與維組的相同元素相關。 </p> <p>範例：Page_Views[ shift(Page, Page_View, Session, 1)="/home" ]是相同工作階段中檢視的下一個頁面為「/home」的頁面檢視次數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level,Group,N) </p> </td> 
   <td colname="col2"> <p>與shift(Dim、Level、Group、N)類似，但如果維中存在空值，則會跳過這些值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> 定義會根據篩選器清單來分類層級元素的維度。 新維度的元素是以引數形式提供的字串。 「層級」的每個元素都與區段維度的第1個元素相關，其篩選條件允許「層級」的元素。 這類似區段視覺效果。 </p> <p>範例：segment（訪客， "一次性訪客" -&gt; Visitor_Sessions = 1, "非常忠誠的訪客" -&gt; Visitor_Sessions &gt; 10, "其他所有人" -&gt; True）會建立一個維度，將訪客分為三組 — 一次性訪客是指只有一個工作階段的訪客，非常忠誠的訪客是指有十個以上工作階段的訪客，而所有其他訪客的值皆為「其他所有人」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>貯體(層級，量度，計數，格式{，開始{，大小}? }) </p> </td> 
   <td colname="col2"> <p>定義一個維，其元素是數字的範圍（例如[0-9]、[10-19]、...）。 「層級」元素與貯體維度的元素相關，其範圍包含該層級元素的「量度」值。 Format是用於格式化量度元素的printf格式字串。 </p> <p>範例：如果Page_Duration_Minutes是表示每頁所花費分鐘數的頁面檢視層級維度，則bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5)是表示每個工作階段所花費分鐘數的工作階段層級維度；其元素為5分鐘間隔<code>{[0-5), [5-10),...,[495-500)}</code>。 </p> <p>Start是第一個間隔的起始值(預設值：0)，而大小是間隔的大小(預設值：1)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>前置詞(Level {,ElementName-&gt;(Prefix{,Prefix}*)}*) </p> </td> 
   <td colname="col2"> <p>定義一個維，其元素是給定的ElementName字串，並與相應的Prefix字串集相關聯。 「級別」的元素與前置詞dim的元素相關，前置詞dim與與級別的指定元素名稱匹配的最長前置詞相關聯。 以特殊字元「$」結尾的前置詞必須完全匹配。 </p> <p>例如，前置詞(URI, "Products" -&gt;("/products/"), "Services" -&gt;("/services/", "/products/service/"), "Warranties" -&gt;("/products/warranty.html$", "/services/warranty.html$", "Everyting Else" -&gt;("/")))會建立將URI分類為四個列出的類別的維度。 各頁面之影響如下： </p> <p>/products/warranty.html進入「保修」，因為它與/products/warranty.html$首碼完全相符。 </p> <p>/products/cars/specialcar.html會進入「產品」，因為它符合/products/首碼，而不再是首碼 </p> <p>/products/service/something.html會進入「服務」，因為它符合/products/service/前置詞，其長度超過/products/前置詞。 </p> <p>/companyinfo/aboutus.html會進入「其他所有項目」類別，因為其符合的唯一首碼為「/」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>延遲（級別，剪輯，維度，篩選， MaxBefore, MaxAfter, FormatString） </p> </td> 
   <td colname="col2"> <p>請參閱<a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a">建立延遲Dimension</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product（分隔符{,Dim}*） </p> </td> 
   <td colname="col2"> <p>定義一個維，其元素是給定維的元素的所有組合（「笛卡爾積」）。 每個元素的名稱由輸入維中對應元素的串連組成，由給定的分隔符字串分隔。 </p> <p>例如，如果維度D1具有元素{"a", "b"}，而維度D2具有元素{"x", "y"}，則笛卡爾積("-", D1, D2)具有元素{"a-x", "a-y", "b-x", "b-y"}。 </p> <p>請注意，在內部，每個輸入維度都會被視為其元素數是二的下一個冪。 這導致笛卡爾積中有一些虛元。 使用Data WorkbenchAPI時，視輸出格式而定，這些元素可能會遭到省略，或顯示為「#nnn」，其中nnn是元素的序數（且用戶端應忽略）。 </p> <p>例如，在上例中，如果D2有三個元素{"x"、"y"、"z"}，則會將其視為有四個元素，而笛卡爾積將有元素{"a-x"、"a-y"、"a-z"、"#3"、"b-x"、"b-y"、"b-z"、"#7"}。 </p> <p>如果未指定任何維，則結果為含有一個元素「#0」的維，等同於「無」維。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nearest_countable(Dim) </p> </td> 
   <td colname="col2"> <p>指已存在的維度：架構中Dim的最接近可數上階。 例如，最接近的可數(URI)與Page_View相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準化(Dim,Count) </p> </td> 
   <td colname="col2"> <p>從非正規維度維度維度定義標準化維度，最多包含計數元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim, TimeMetric, FormatString, Count, Offset, TrimToData {, WeekStart}?) </p> </td> 
   <td colname="col2"> <p>定義一個維，該維包含維Dim的元素子集，其元素表示時間片段，例如天、周或年。 </p> <p>子集是指定時間（常數量度TimeMetric的值）的範圍，該值被解釋為自1970年1月1日午夜UTC以來的秒數時間值。 此範圍包含「計數」元素，最後一個元素是指定維的元素之後的「偏移」元素，其名稱是將量度值格式化為指定FormatString字串的結果。 FormatString使用與標準C庫函式strftime相同的%逸出。 </p> <p>如果trimToData為true，則將刪除所生成尺寸開頭（即「尺寸」開頭之前）的任何元素。 若為false，則一律會有Count指定的確切元素數。 請注意，產生的維度末端可能總是有實際不在「尺寸」中的元素。 </p> <p>如果指定，可選的WeekStart必須是{ "Sun"、"Mon"、"Tue"、"Wed"、"Thu"、"Fri"、"Sat" }之一。 它會將TimeMetric回移至該工作日的最近一次事件，借此修改TimeMetric。 </p> <p>範例：如果「周」的元素為{ "10/03/10"、"10/10/10"、...、"12/12/10" }，且內置「截止」度量值為1292348109（代表2010年12月14日中旬的時間），則最後n(Week、As_Of、"%m/%d/%y"、4, 0, false, "Sun")使用元素{ 12/12/10"、"12/19/10"、"12/23/10"、"12/30/10" }定義維。 </p> <p>範例2:如果「周」維只包含元素{"12/19/10"、"12/26/10"、...、"01/30/11"}，且「截止」度量如上，則最近n(Week、As_Of、"%m/%d/%y"、4,0, true、"Sun")會提供包含元素{"12/19/10"、"12/23/10"、"12/30/10"}的維。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>定義一個維，該維包含維元素的子集，其元素表示天。 子集是指定時間（常數量度TimeMetric的值）的範圍，該值被解釋為自1970年1月1日午夜UTC以來的秒數時間值。 範圍會包含指定時間前nMonths中每天對應的元素。 如果includeThisMonth為true，則範圍也會包含該月中包含指定時間的每一天。 </p> <p>FormatString指定維元素的格式，使用「%」逸出，如標準C庫函式字串中。 </p> <p>如果trimToData為true，則將刪除所生成尺寸開頭（即「尺寸」開頭之前）的任何元素。 若為false，則一律會有Count指定的確切元素數。 請注意，產生的維度末端可能總是有實際不在「尺寸」中的元素。 </p> <p>範例：如果Day的元素為{ "01/01/10"、"01/02/10"、........................................................................................................................................................................................................................................... </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim, TimeMetric, FormatString, allMonth, trimToData) </p> </td> 
   <td colname="col2"> <p>與前幾個月的天數類似，但元素只對應與TimeMetric所指定的時間相同月份的天數。 如果allMonth為true，則適當月份的每一天都會有元素；否則，只有從適當月份的第一天到包含指定時間的當天，才會是維度的一部分。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_months(Dim, TimeMetric, FormatString, nMonths, includeThisMonth, TrimToData) </p> </td> 
   <td colname="col2"> <p>與前幾個月的天數類似，只是這些元素對應到月份之後的天數，而非之前的天數，該月包含TimeMetric指定的時間。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>定義一個維，該維包含維元素的子集，其元素表示小時。 子集是指定時間（常數量度TimeMetric的值）的範圍，該值被解釋為自1970年1月1日午夜UTC以來的秒數時間值。 範圍包含與nDaysForward一天之後的每小時對應的元素，包含TimeMetric指定的時間。 </p> <p>FormatString指定維元素的格式，使用「%」逸出，如標準C庫函式字串中。 格式字串應一律輸出字串，代表傳入時間當天開始的午夜。 </p> <p>如果trimToData為true，則將刪除所生成尺寸開頭（即「尺寸」開頭之前）的任何元素。 若為false，則一律會有Count指定的確切元素數。 請注意，產生的維度末端可能總是有實際不在「尺寸」中的元素。 </p> <p>範例：如果「小時」有元素{ "01/01/10 00:00"、"01/01/10 01:00"、...............................................................................................................................................................................................................................0" }。 </p> </td> 
  </tr> 
 </tbody> 
</table>
