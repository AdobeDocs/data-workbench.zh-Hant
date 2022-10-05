---
description: 流量設定檔包含下列量度以識別訪客流量。
title: 流量設定檔量度
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '709'
ht-degree: 2%

---

# 流量設定檔量度{#traffic-profile-metrics}

{{eol}}

流量設定檔包含下列量度以識別訪客流量。

<table id="table_D981FB9F8B734E3C845A9628548565F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 量度 </th> 
   <th colname="col2" class="entry"> 量度公式和層級 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 登入點 </td> 
   <td colname="col2">公式： <span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>級別：頁面檢視 </p></td> 
   <td colname="col3"> 在每個頁面上進入網站的工作階段數。 此量度僅會透過「頁面」維度評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出率 </td> 
   <td colname="col2">公式： <span class="filepath"> 退出點/頁面檢視 </span><p>級別：頁面檢視 </p></td> 
   <td colname="col3"> 從每個頁面退出網站的工作階段百分比。 「退出率」量度只能透過頁面維度來評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出點 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>級別：頁面檢視 </p></td> 
   <td colname="col3"> 從每個頁面退出網站的工作階段數。 此量度僅會透過「頁面」維度評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">公式： <span class="filepath"> (原始（訪客） — ((原始（訪客）+ .69)^0.5 * 1.281551 - 1.2269))*(訪客/原始（訪客）)</span><p>級別：訪客 </p></td> 
   <td colname="col3"> 由Insight報告的最低可能訪客數量的測量。 數學上來說，它會指定機率為90%的最低訪客數量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面檢視持續時間 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> sum(exact_page_duration, page_view)*0.1/Page_Views[任何Exact_Page_Duration]</span></p> <p>級別：頁面檢視 </p> </td> 
   <td colname="col3"> 特定頁面或一組頁面所花費的平均時間長度(MM:SS)。 此量度僅會透過「頁面」維度評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每個工作階段的頁面檢視次數 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> Page_Views/（按Page_View列出的會話） </span></p> <p>級別：工作階段 </p> </td> 
   <td colname="col3"> 具有頁面檢視之每個工作階段中的平均頁面檢視次數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面檢視次數 </td> 
   <td colname="col2">公式： <span class="filepath"> sum(One, Page_View)</span><p>級別：頁面檢視 </p></td> 
   <td colname="col3"> 頁面檢視次數。 頁面檢視是對已定義頁面的要求（不會計入影像存取權和其他類型的篩選內容）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面檢視百分比 </td> 
   <td colname="col2">公式： <span class="filepath"> Page_Views/total(Page_Views) </span><p>級別：頁面檢視 </p></td> 
   <td colname="col3"> 頁面檢視的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 會話百分比 </td> 
   <td colname="col2">公式： <span class="filepath"> 工作階段/總計（工作階段）</span><p>級別：工作階段 </p></td> 
   <td colname="col3"> 工作階段的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客百分比 </td> 
   <td colname="col2">公式： <span class="filepath"> 訪客/總計（訪客） </span><p>級別：訪客 </p></td> 
   <td colname="col3"> 訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PCT引用的訪客 </td> 
   <td colname="col2"> <p>公式：反向連結訪客/訪客 </p> <p>級別：訪客 </p> </td> 
   <td colname="col3"> 從其他網站轉介至此網站的訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參考的工作階段 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> 工作階段[Referrer&lt;&gt; 'None' and Referrer&lt;&gt;'bookmarks']</span></p> <p>級別：工作階段 </p> </td> 
   <td colname="col3"> 從其他網站轉到此網站的工作階段數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 反向連結訪客 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> 訪客[Visitor_ Referrer&lt;&gt;'None'及Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>級別：訪客 </p> </td> 
   <td colname="col3"> 從其他網站轉介到此網站的訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 保留 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> 工作階段[shift（無，Ses,Visitor,1）= ""] /工作階段</span></p> <p>級別：工作階段 </p> </td> 
   <td colname="col3"> 非訪客上次工作階段的工作階段百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段期間 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> (sum(Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>級別：工作階段 </p> </td> 
   <td colname="col3">訪客在工作階段中逗留的平均時間(MM:SS)。 <p><p>注意：您可以將此量度與 <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external"> 區段匯出</a> 功能。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 依頁面檢視的工作階段 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> 按頁面檢視的工作階段</span></p> <p> 級別：工作階段 </p> </td> 
   <td colname="col3"> 具有頁面檢視的工作階段數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> sum（1，會話）</span></p> <p>級別：工作階段 </p> </td> 
   <td colname="col3"> 訪客工作階段的計數。 工作階段是網站中一個訪客的活動期間。 系統會使用Cookie、逾時和其他試探法來識別每個訪客的個別工作階段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> 信賴度（工作階段）* 1.281551 /工作階段</span></p> <p>級別：訪客 </p> </td> 
   <td colname="col3"> Data Workbench所報告的「工作階段」量度的信賴度。 從數學上講，它是一個+/ — 百分比，指定實際答案將在80%的時間內的範圍。 按照經驗，將SCI80百分比加倍，將給出一個範圍，實際答案將是99%的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> (((原始（訪客）+ .68)^0.5 * 1.281551 + 1.2269)+原始（訪客）)*(訪客/原始（訪客）)</span></p> <p>級別：訪客 </p> </td> 
   <td colname="col3"> 由Insight報告的最大可能訪客數的測量。 數學上，它會指定90%機率的訪客最多。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">公式： <span class="filepath"> ((原始（訪客）+ .68)^0.5 * 1.281551 + 1.2269)/原始（訪客）</span><p>級別：訪客 </p></td> 
   <td colname="col3"> 由Insight報告的訪客量度的信賴度測量。 從數學上講，它是一個+/ — 百分比，指定實際答案將在80%的時間內的範圍。 根據經驗，將VCI80百分比加倍將給出一個範圍，在此範圍內，實際答案將佔99%的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 依頁面檢視的訪客 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> 依Page_View的訪客</span></p> <p>級別：頁面檢視 </p> </td> 
   <td colname="col3"> 有頁面檢視的訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 依工作階段的訪客 </td> 
   <td colname="col2"> <p>公式： <span class="filepath"> 依工作階段的訪客 </span></p> <p>級別：工作階段 </p> </td> 
   <td colname="col3"> 具有工作階段的訪客數。 </td> 
  </tr> 
 </tbody> 
</table>
