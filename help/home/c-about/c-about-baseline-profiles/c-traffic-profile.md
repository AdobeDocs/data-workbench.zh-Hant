---
description: 「流量」描述檔包含下列量度以識別訪客流量。
title: 流量設定檔量度
uuid: 7dfa18ef-d2cd-44ae-8c56-a0630a9d5cf2
exl-id: 38f191e5-5b30-4fe0-a680-bcb33fe52eca
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 2%

---

# 流量設定檔量度{#traffic-profile-metrics}

「流量」描述檔包含下列量度以識別訪客流量。

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
   <td colname="col2">公式：<span class="filepath"> Page_Views[no shift(None,Page_View, Session,-1)]</span><p>層級：頁面檢視 </p></td> 
   <td colname="col3"> 在每個頁面上輸入網站的作業數。 此度量僅會在「頁面」維度上評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出率 </td> 
   <td colname="col2">公式：<span class="filepath">退出次數／頁面檢視次數</span><p>層級：頁面檢視 </p></td> 
   <td colname="col3"> 退出網站的作業從每個頁面的百分比。 「退出率」度量只能評估在頁面維度上。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 退出點 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_Views[no shift(None,Page_View, Session,1)] </span><p>層級：頁面檢視 </p></td> 
   <td colname="col3"> 從每個頁面退出網站的作業數。 此度量僅會在「頁面」維度上評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LVCI90 </td> 
   <td colname="col2">公式：<span class="filepath">(原始（訪客）-((原始（訪客）+ .69)^0.5 * 1.281551 - 1.2269))*(訪客／原始（訪客）)</span><p>層級：訪客 </p></td> 
   <td colname="col3"> 由Insight報告的最低訪客數量度量。 以數學計算，它會指定概率為90%的最低訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面檢視持續時間 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> sum(exact_page_duration, page_view)*0.1/Page_Views[any Exact_Page_Duration]</span></p> <p>層級：頁面檢視 </p> </td> 
   <td colname="col3"> 特定頁面或頁面群組所花費的平均時間長度(MM:SS)。 此度量僅會在「頁面」維度上評估。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每個作業的頁面檢視次數 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> Page_Views/(Sessions by Page_View)</span></p> <p>層級：會話 </p> </td> 
   <td colname="col3"> 具有頁面檢視的每個作業中的平均頁面檢視次數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面檢視 </td> 
   <td colname="col2">公式：<span class="filepath"> sum(One, Page_View)</span><p>層級：頁面檢視 </p></td> 
   <td colname="col3"> 頁面檢視次數。 頁面檢視是對已定義頁面的要求（不會計入影像存取及其他類型的篩選內容）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面檢視次數百分比 </td> 
   <td colname="col2">公式：<span class="filepath"> Page_Views/total(Page_Views)</span><p>層級：頁面檢視 </p></td> 
   <td colname="col3"> 頁面檢視的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 會話數 </td> 
   <td colname="col2">公式：<span class="filepath">會話數／總計（會話數）</span><p>層級：會話 </p></td> 
   <td colname="col3"> 作業的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客百分比 </td> 
   <td colname="col2">公式：<span class="filepath">訪客／總計（訪客）</span><p>層級：訪客 </p></td> 
   <td colname="col3"> 訪客的百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參考訪客百分比 </td> 
   <td colname="col2"> <p>公式：反向連結訪客／訪客 </p> <p>層級：訪客 </p> </td> 
   <td colname="col3"> 從其他網站反向連結至此網站的訪客百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 參考的會話 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">工作階段[Referrer&lt;&gt; 'None'和Referrer&lt;&gt;'bookmarks']</span></p> <p>層級：會話 </p> </td> 
   <td colname="col3"> 從其他網站引薦至此網站的作業數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 反向連結訪客 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">訪客[Visitor_ Referrer&lt;&gt;'None'和Visitor_Referrer&lt;&gt;'book marks']</span></p> <p>層級：訪客 </p> </td> 
   <td colname="col3"> 從其他網站反向連結至此網站的訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 保留 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">工作階段[shift(None,Ses,Visitor,1)= ""] /工作階段</span></p> <p>層級：會話 </p> </td> 
   <td colname="col3"> 非訪客上次作業的作業百分比。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段持續時間 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">(sum(Exact_Page_Duration, Session)*.1/Sessions)[Session_ Duration &lt;= '01:00:00']</span></p> <p>層級：會話 </p> </td> 
   <td colname="col3">訪客在作業中所花費的平均時間長度(MM:SS)。 <p><p>注意：您可將此度量與<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Segment_Export" format="http" scope="external">區段匯出</a>功能搭配使用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 按頁面檢視的作業 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">按Page_View列出的會話</span></p> <p> 層級：會話 </p> </td> 
   <td colname="col3"> 具有頁面檢視的作業數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段 </td> 
   <td colname="col2"> <p>公式：<span class="filepath"> sum(One, Session)</span></p> <p>層級：會話 </p> </td> 
   <td colname="col3"> 訪客工作階段的計數。 工作階段是網站一位訪客的活動期間。 使用Cookie、逾時和其他啟發式方法識別每個訪客的個別工作階段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SCI80 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">信賴（工作階段）* 1.281551 /工作階段</span></p> <p>層級：訪客 </p> </td> 
   <td colname="col3"> 資料工作台所報告之「工作階段」度量的信賴度量。 從數學上講，這是一個+/-百分比，它指定了實際答案在80%的時間內的範圍。 根據經驗，將SCI80百分比提高一倍，將給出一個範圍，實際答案將佔99%的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> UVCI90 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">(((原始（訪客）+ .68)^0.5 * 1.281551 + 1.2269)+原始（訪客）)*(訪客／原始（訪客）)</span></p> <p>層級：訪客 </p> </td> 
   <td colname="col3"> 由Insight報告的最高訪客數量度量。 從數學上來看，它會指定概率為90%的最高訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VCI80 </td> 
   <td colname="col2">公式：<span class="filepath">((原始（訪客）+ .68)^0.5 * 1.281551 + 1.2269)/原始（訪客）</span><p>層級：訪客 </p></td> 
   <td colname="col3"> 前瞻分析所報告之訪客量度的信賴度量。 從數學上講，這是一個+/-百分比，它指定了實際答案在80%的時間內的範圍。 根據經驗法則，將VCI80百分比加倍將給出一個範圍，在此範圍內，實際答案將佔99%的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 依頁面檢視的訪客 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">依Page_View的訪客</span></p> <p>層級：頁面檢視 </p> </td> 
   <td colname="col3"> 具有頁面檢視的訪客數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 依作業的訪客 </td> 
   <td colname="col2"> <p>公式：<span class="filepath">依工作階段的訪客</span></p> <p>層級：會話 </p> </td> 
   <td colname="col3"> 具有作業的訪客數。 </td> 
  </tr> 
 </tbody> 
</table>
