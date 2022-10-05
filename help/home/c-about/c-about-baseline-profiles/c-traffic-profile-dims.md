---
description: 流量設定檔包含下列維度，以協助識別訪客動作。
title: 流量設定檔維度
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
exl-id: 1e7d2904-aa5d-4848-a398-5d4669953be9
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '987'
ht-degree: 8%

---

# 流量設定檔維度{#traffic-profile-dimensions}

{{eol}}

流量設定檔包含下列維度，以協助識別訪客動作。

下表中的維定義在轉換資料集的Traffic\Dataset\Transformation目錄中包含檔案。

| 名稱 | 類型 | 層級 | 說明 |
|---|---|---|---|
| 日 | 簡單 | 工作階段 | 工作階段第一個記錄項目的日期。 |
| 星期 | 簡單 | 工作階段 | 工作階段第一個記錄項目的一週中的某天。 |
| 確切的頁面持續時間（隱藏） | 數值 | 頁面瀏覽數 | 頁面檢視的持續時間（以毫秒為單位），從該頁面檢視的時間減去下一個頁面檢視的時間。 工作階段中最後一個頁面檢視的確切持續時間一律為0。 |
| 小時 | 簡單 | 工作階段 | 工作階段第一個記錄項目的小時。 |
| 小時 | 簡單 | 工作階段 | 工作階段第一個記錄項目的一小時。 |
| 月 | 簡單 | 工作階段 | 工作階段第一個記錄項目的月份。 |
| 頁面瀏覽數 | 可數 | 工作階段 | 滿足頁面檢視條件的記錄項目或「事件資料記錄」。 |
| 反向連結 | 簡單 | 工作階段 | 工作階段第一個記錄項目之反向連結的第二層級網域（若為內部反向連結網域，則為無）。 |
| 工作階段 | 可數 | 訪客 | 訪客相關連續活動的時段。 其分隔方式為閒置30分鐘、外部反向連結網域或最長48小時的工作階段期間。 可在 [!DNL Transformation.cfg] 檔案。 |
| URI | 簡單 | 頁面瀏覽數 | 頁面檢視的URI主體。 可使用ReplaceURI、PrependURI和AppendURI轉換來重定義URI維。 |
| 訪客 | 可數 | 不適用 | x-trackingid的唯一值。 若使用永久性Cookie，則通常對應至不重複瀏覽器。 x-trackingid則可以以IP號碼或某些其他唯一識別碼（例如x.509公用名稱）為基礎。 |
| 週 | 簡單 | 工作階段 | 工作階段第一個記錄項目的周。 |

下表中的維在流量配置檔案的Dimension目錄中定義：

<table id="table_02AC8DAD1B62443A96FABCB75C37F23A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 維度 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col03" class="entry"> 層級 </th> 
   <th colname="col3" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 瀏覽器 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 訪客使用的使用者代理類型，包括版本號碼（例如MSIE 6.0）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 瀏覽器類型 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 訪客使用的使用者代理類型（例如MSIE）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜尋引擎 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03">工作階段 <p>第一列 </p></td> 
   <td colname="col3"> 訪客從已命名的搜尋引擎搜尋時，訪客工作階段中的第一個搜尋引擎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 下一個URI </td> 
   <td colname="col2"> 派生（基於URI維的ShiftDim） </td> 
   <td colname="col03"> 頁面瀏覽數 </td> 
   <td colname="col3"> 當前選定URI之後的下一個URI的URI。 此衍生維度用於分析訪客在任何指定URI後接做什麼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一次性與重複 </td> 
   <td colname="col2"> 衍生（根據重複訪客和一次性訪客量度的SegmentDim） </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 訪客的類型：一次或重複。 一次性訪客在網站上只有一個工作階段，而重複訪客有多個工作階段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面 </td> 
   <td colname="col2"> 派生（基於URI維的RenameDim） </td> 
   <td colname="col03"> 頁面瀏覽數 </td> 
   <td colname="col3"> 工作階段期間造訪的每個頁面的名稱。 最初，每個頁的名稱與URI相同，但可以更改以便更輕鬆地解釋。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 反向連結 </td> 
   <td colname="col2"> 繼承自內建反向連結維度 </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> 第一次將工作階段反向連結至網站的網站的第二層網域名稱（由訪客的瀏覽器提供）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜尋片語 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03">工作階段 <p>第一列 </p></td> 
   <td colname="col3"> 訪客從已命名的搜尋引擎搜尋時，搜尋引擎所傳遞的訪客工作階段中的第一個搜尋片語。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜尋詞 </td> 
   <td colname="col2"> 多對多 </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> 當訪客從已命名的搜尋引擎點進搜尋反向連結時，搜尋引擎傳遞的每個搜尋詞。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段期間 </td> 
   <td colname="col2"> 衍生（根據確切頁面持續時間量度的MetricDim） </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> 以30秒為單位的工作階段期間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段數 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> 訪客瀏覽網站的次數。 例如，首次訪客的工作階段數為「1」，第二次訪客的工作階段數為「2」，以此類推。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段頁面檢視 </td> 
   <td colname="col2"> 衍生（根據頁面檢視量度的MetricDim） </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> 工作階段中的頁面檢視次數。 例如，在「工作階段頁面檢視」維度中選取「3」時，會選取具有3個頁面檢視的所有工作階段。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜尋引擎 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> 第一個網站的第二層網域名稱，這是指在工作階段期間將訪客反向連結至網站的命名搜尋引擎（由訪客的瀏覽器提供）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間維度 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> 工作階段開始的小時、日、小時、周、周、日、月、季或年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間報表Dimension </td> 
   <td colname="col2"> 衍生（根據內建時間維度重新命名維度） </td> 
   <td colname="col03"> 工作階段 </td> 
   <td colname="col3"> Dimension包括天前，上個月的天，上週的天，上週的天，本週的天，今天的天，上週的小時，昨天的小時，過去12個月，過去2個月，過去2週，過去24小時，過去3個月，過去4週，過去6個月，過去7天，過去7天，今天，過去8週，過去9個月，上週，本月，本月，這個和過去14天、這個和過去6個月、這個和過去8週、今天、今天報表、今天和過去30天、周前和昨天，是您輕鬆建立工作區或報表的方式，此報表一律會顯示資料集中的一部分資料。 每個會根據工作階段開始的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 繼承自內置DimensionURI </td> 
   <td colname="col03"> 頁面瀏覽數 </td> 
   <td colname="col3"> 已檢視之每個頁面的URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客頁面檢視 </td> 
   <td colname="col2"> 衍生（根據頁面檢視量度的MetricDim） </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 訪客目前的頁面檢視次數。 例如，在「訪客頁面檢視」維度中選取「3」，便會在其所有工作階段中選取具有3個頁面檢視的所有訪客。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客反向連結 </td> 
   <td colname="col2"> 繼承自內建維度反向連結 </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 網站的第二層網域名稱，首先將訪客反向連結至網站進行其第一個工作階段（由訪客的瀏覽器提供）。 </td> 
  </tr> 
 </tbody> 
</table>
