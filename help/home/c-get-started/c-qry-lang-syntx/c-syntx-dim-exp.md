---
description: Dimension運算式絕不單獨使用，但可用於任何在量度或篩選運算式中呼叫維度的位置。
title: 維度運算式的語法
uuid: c437cc52-4eb3-4202-a0b4-e23889f9c8a2
exl-id: 58609e31-8ad8-418b-9a9f-40462d6443f7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1855'
ht-degree: 0%

---

# 維度運算式的語法{#syntax-for-dimension-expressions}

Dimension運算式絕不單獨使用，但可用於任何在量度或篩選運算式中呼叫維度的位置。

1. 在運算式文字中應輸入帶底線的字詞。
1. `{TEXT}?`表示可選文本。
1. `{TEXT}*`表示可能發生零次或多次的文字。
1. `{A | B | C |...}`表示由給定選項（如A或B或C）中的一個完全組成的文本。.
1. 表單`[A,B)`表示數字範圍，從A到但不包括B。

<table id="table_2D9AE1E2397843C284E838330370A1EE"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>識別碼 </p> </td> 
   <td colname="col2"> <p>標識符引用命名維。 有關管理法律標識符的規則，請參見<a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8">標識符的語法</a>。 </p> <p>範例：會話數[ Session_Number = "1" ]是會話數為"1"的會話數。 會話編號是標識符引用的命名維。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(維度) </p> </td> 
   <td colname="col2"> <p>(Dimension)的結果與Dimension的結果相同。 括弧指定運算式中的運算順序。 </p> <p>範例：會話數[(Page)= "/home" ]是訪問頁面"/home"的會話數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>依層級調整尺寸 </p> </td> 
   <td colname="col2"> <p>定義一個尺寸，其元素與尺寸「尺寸」(Dim)相同，但通過尺寸級別與其他尺寸相關。 </p> <p>具體來說，新維度的元素與級別元素的相同元素有關，並且與任何其他維度的元素有關，這些元素與這些級別元素中的任何元素有關。 </p> <p>範例：Sessions[(Page by Visitor)="/home" ]是瀏覽頁面"/home"的訪客的Sessions數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>shift(Dim,Level, Group,N) </p> </td> 
   <td colname="col2"> <p>定義與尺寸「尺寸」(Dim)具有相同元素的尺寸。 維級別的eth元素與新維的相同元素有關，而維的e+N元素與級別的e+N元素有關，前提是級別的eth和e+N元素與維組的相同元素有關。 </p> <p>範例：Page_Views[ shift(Page, Page_View, Session, 1)="/home" ]是「頁面檢視」的數目，在相同作業階段中檢視的下一頁為「/home」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>next(Dim,Level, Group, N) </p> </td> 
   <td colname="col2"> <p>與shift(Dim,Level,Group,N)類似，但是如果維中有空值，則會跳過這些值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>segment(Level {,String-&gt;Filter}*) </p> </td> 
   <td colname="col2"> <p> 定義維度，根據篩選清單來分類「層級」元素。 新維的元素是作為參數給定的字串。 「層級」的每個元素都與區段維度的第一個元素相關，其篩選器會接納「層級」元素。 這類似區段視覺化。 </p> <p>範例：segment（訪客，"One-Time Visitors" -&gt; Visitor_Sessions = 1, "Very Loyal Visitors" -&gt; Visitor_Sessions &gt; 10, "Everyone Else" -&gt; True）會建立將訪客分為三個群組的維度——一次性訪客是僅有十個作業的訪客，非常忠誠的訪客是有十個作業的訪客，其他所有訪客的值為「其他人」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>bucket(Level, Metric, Count, Format {, Start {, Size}? }?) </p> </td> 
   <td colname="col2"> <p>定義其元素是數字範圍（如[0-9]、[10-19]、...）的維。 「級別」元素與桶維的元素相關，其範圍包含該級別元素的「度量」值。 「格式」是用於格式化「量度」元素的printf格式字串。 </p> <p>範例：如果Page_Duration_Minutes是代表每頁逗留分鐘數的頁面檢視層級維度，則bucket(Session, sum(Page_Duration_Minutes, Page_View), 100, "%0.0f minutes", 0, 5)是表示每個作業中逗留分鐘數的作業層級維度；其元素為5分鐘間隔<code>{[0-5), [5-10),...,[495-500)}</code>。 </p> <p>開始是第一個間隔的開始值(預設值：0)，而大小是間隔的大小(預設值：1)。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>prefix(Level {,ElementName-&gt;(Prefix{,Prefix}*)}*) </p> </td> 
   <td colname="col2"> <p>定義一個維，其元素是給定的ElementName字串，並與相應的Prefix字串集相關聯。 「級別」元素與前置詞維的元素相關，前置詞維與與給定級別元素名稱匹配的最長前置詞相關聯。 必須以特殊字元「$」結尾的字首必須完全相符。 </p> <p>例如，前置詞(URI, "Products" -&gt;("/products/"), "Services" -&gt;("/services/", "/products/service/"), "Warranties" -&gt;("/products/warranty.html$", "/services/warranty.html$", "Everyting Else" -&gt;("/")))會建立一個將URI分類到所列四個類別的維度。 對各種頁面的影響如下： </p> <p>/products/warranty.html進入保修，因為它與/products/warranty.html$首碼完全相符。 </p> <p>/products/cars/specialcar.html進入「產品」，因為它符合/products/首碼，而不再符合首碼 </p> <p>/products/service/something.html會進入「服務」，因為它與/products/service/前置詞匹配，該前置詞比/products/前置詞長。 </p> <p>/companyinfo/aboutus.html會進入「Everything Else」類別，因為它符合的唯一首碼是「/」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>延遲（等級、剪輯段、尺寸、篩選、MaxBefore、MaxAfter、FormatString） </p> </td> 
   <td colname="col2"> <p>請參閱<a href="../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/t-create-ltncy-dims.md#task-6d46ea8c89a047318d9c71bf105ef64a">建立延遲Dimension</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cartesian_product（分隔符{,Dim}*） </p> </td> 
   <td colname="col2"> <p>定義一個尺寸，其元素是給定尺寸的元素的所有組合（「笛卡爾積」）。 每個元素的名稱由輸入維中相應元素的串連組成，由給定的分隔符串分隔。 </p> <p>例如，如果維度D1包含元素{"a", "b"}，而維度D2包含元素{"x", "y"}，則笛卡爾積("-", D1, D2)包含元素{"a-x", "a-y", "b-x", "b-y"}。 </p> <p>請注意，在內部，每個輸入尺寸都會被視為其元素數是二的下一個較高冪。 這導致笛卡爾積具有一些虛元素。 使用Data WorkbenchAPI時，這些元素可能會被省略，或顯示為"#nnn"，其中nnn是元素的序數（客戶端應忽略）。 </p> <p>例如，在上例中，如果D2有三個元素{"x"、"y"、"z"}，則會將其視為有四個元素，而笛卡爾積將有元素{"a-x"、"a-y"、"a-z"、"#3"、"b-x"、"b-y"、"b-z"、"#7"}。 </p> <p>如果未給出維，則結果是一個含有"#0"元素的維，該元素等效於「無」維。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>nearest_countable(Dim) </p> </td> 
   <td colname="col2"> <p>指已存在的維：模式中Dim的最近可計數祖先。 例如，最接近的可計數(URI)與Page_View相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>標準化(Dim,Count) </p> </td> 
   <td colname="col2"> <p>從非正規維度Dim定義標準化維度，最多包含「計數」元素。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>last_n(Dim、TimeMetric、FormatString、Count、Offset、TrimToData {、WeekStart}?) </p> </td> 
   <td colname="col2"> <p>定義一個維，該維包含維Dim的元素子集，其元素表示時間片段，例如天、周或年。 </p> <p>子集是指在指定時間附近的範圍，即常數量度TimeMetric的值，此值會解讀為自1970年1月1日午夜以來以秒為單位的時間值。 此範圍包含「計數」元素，其中最後一個元素是指定Dim元素之後的「偏移」元素，其名稱是使用指定的FormatString字串格式化量度值的結果。 FormatString使用與標準C庫函式strftime相同的%轉義。 </p> <p>如果trimToData為true，則會移除產生尺寸開頭（在「尺寸」開頭之前）的任何元素。 若為false，則一律會有「計數」所指定的確切元素數。 請注意，最終尺寸的結尾處可能始終存在實際不在「尺寸」(Dim)中的元素。 </p> <p>如果指定了可選WeekStart，則必須是{ "Sun"、"Mon"、"Tue"、"Wed"、"Thu"、"Fri"、"Sat" }中的一個。 它會將TimeMetric向後移至該工作日的最近一次事件，以修改TimeMetric。 </p> <p>範例：如果「周」包含元素{ "10/03/10"、"10/10/10"、..., "12/12/10" }，而內建「截止」量度的值為1292348109（代表12月14日中旬的某次， 2010），然後最後n(Week, As_Of, "%m/%d/%y", 4, 0, false, "Sun")定義含元素{ "12/12/12/19/10", "12/23/10", "12/30/10" }。 </p> <p>範例2:如果「周」維度只包含元素{"12/19/10"、"12/26/10"、..., "01/30/11"}，而「截止」度量如上，則最後n(Week、As_Of、"%m/%d/%y"、4、0、true、sun")提供含元素{"12/19/10"、"12/23/10"、"12/30/10"}的維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_previous_months(Dim、TimeMetric、FormatString、nMonths、includeThisMonth、TrimToData) </p> </td> 
   <td colname="col2"> <p>定義一個維，該維包含「尺寸」元素的子集，其元素代表天數。 子集是指在指定時間附近的範圍，即常數量度TimeMetric的值，此值會解讀為自1970年1月1日午夜以來以秒為單位的時間值。 該範圍將包含與指定時間前nMonths月中每天對應的元素。 如果includeThisMonth為true，則範圍也會包含包含指定時間的月份中的每一天。 </p> <p>FormatString指定Dim元素的格式，使用標準C庫函式strftime中的"%"轉義。 </p> <p>如果trimToData為true，則會移除產生尺寸開頭（在「尺寸」開頭之前）的任何元素。 若為false，則一律會有「計數」所指定的確切元素數。 請注意，最終尺寸的結尾處可能始終存在實際不在「尺寸」(Dim)中的元素。 </p> <p>範例：如果Day包含元素{ "01/01/10"、"01/02/10"、...... "12/31/10" }，而內建「截止日期」量度的值為1292348109（代表12月14日中午的時間）, 2010)，則前幾個月的天數(Day, As_Of, "%m/%d/%y", 2, false, false)將包含元素{ "10/01/10", "10/02/10", ..., "11/30/10" }。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_current_month(Dim、TimeMetric、FormatString、allMonth、trimToData) </p> </td> 
   <td colname="col2"> <p>與前幾個月的天數類似，但元素只對應與TimeMetric所指定時間相同月份的天數。 若allMonth為true，則適當月份的每一天都會有元素；否則，只有從適當月份的第一天到包含指定時間的那一天的天數才會屬於維度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>days_of_future_months(Dim、TimeMetric、FormatString、nMonths、includeThisMonth、TrimToData) </p> </td> 
   <td colname="col2"> <p>與前幾個月的天數類似，但元素對應的是包含TimeMetric所指定時間的月份之後（而非之前）的天數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>hours_of_day(Dim, Metric, TimeFormatString, nDaysForward, TrimData) </p> </td> 
   <td colname="col2"> <p>定義一個維，該維包含「尺寸」元素的子集，其元素代表小時。 子集是指在指定時間附近的範圍，即常數量度TimeMetric的值，此值會解讀為自1970年1月1日午夜以來以秒為單位的時間值。 此範圍包含與一天後nDaysForward的每小時對應的元素，其中包含TimeMetric所指定的時間。 </p> <p>FormatString指定Dim元素的格式，使用標準C庫函式strftime中的"%"轉義。 格式字串應一律輸出一個字串，代表傳入時間當天開始的午夜。 </p> <p>如果trimToData為true，則會移除產生尺寸開頭（在「尺寸」開頭之前）的任何元素。 若為false，則一律會有「計數」所指定的確切元素數。 請注意，最終尺寸的結尾處可能始終存在實際不在「尺寸」(Dim)中的元素。 </p> <p>範例：如果「小時」有元素{ "01/01/10 00:00"、"01/01/10 01:00"、...、"12/31/10 23:00" }，而內建「開始於」量度的值為1292348109（代表2010年12月14日中旬的時間），然後是一天中的小時(Hour, As_Of, "%x 00:00", 0, false)包含元素{ "12/12/10 00:00", "12/12/101:00", ..., "12/12/10 23:00" }。 </p> </td> 
  </tr> 
 </tbody> 
</table>
