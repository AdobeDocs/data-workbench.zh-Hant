---
description: 「流量」描述檔包含下列維度，可協助識別訪客動作。
solution: Analytics
title: 流量描述檔維度
topic: Data workbench
uuid: 9c0dabfc-67c9-4772-99ac-4c503c06ea78
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 流量描述檔維度{#traffic-profile-dimensions}

「流量」描述檔包含下列維度，可協助識別訪客動作。

下表中的維度是在轉換資料集中定義的，包含Traffic\Dataset\Transformation directory中的檔案。

| 名稱 | 類型 | 層級 | 說明 |
|---|---|---|---|
| 日 | 簡單 | 作業階段 | 會話的第一個日誌條目的日期。 |
| 星期 | 簡單 | 作業階段 | 工作階段第一個記錄項目的一週中的某天。 |
| 完全頁面持續時間（隱藏） | 數值 | 頁面檢視 | 頁面檢視的持續時間（以毫秒為單位），測量方式是從該頁面檢視的時間中減去下一頁檢視的時間。 工作階段中最後一個頁面檢視的確切持續時間永遠為0。 |
| 小時 | 簡單 | 作業階段 | 會話的第一個日誌條目的小時。 |
| 小時 | 簡單 | 作業階段 | 工作階段第一個記錄項目的一天中的某小時。 |
| 月 | 簡單 | 作業階段 | 作業的第一個記錄項目的月份。 |
| 頁面檢視 | 可計數 | 作業階段 | 滿足頁面檢視條件的記錄項目或「事件資料記錄」。 |
| 反向連結 | 簡單 | 作業階段 | 作業階段第一個記錄項目之反向連結的第二層級網域（若是內部反向連結網域，則為無）。 |
| 作業階段 | 可計數 | 訪客 | 訪客的相關連續活動的時段。 它以閒置30分鐘和外部反向連結網域或最長48小時作業持續時間來分隔。 這些逾時和被認為是內部網域的網域集都可以在檔案中設 [!DNL Transformation.cfg] 定。 |
| URI | 簡單 | 頁面檢視 | 頁面檢視的URI幹線。 URI維可以使用ReplaceURI、PrependURI和AppendURI轉換來重定義。 |
| 訪客 | 可計數 | 不適用 | x-trackingid的唯一值。 使用永久性Cookie時，通常對應至唯一瀏覽器。 x-trackingid可以以其他方式根據IP編號或某些其他唯一識別碼，例如x.509公用名稱。 |
| 週 | 簡單 | 作業階段 | 工作階段第一個記錄項目的周。 |

下表中的維定義在流量描述檔的維目錄中：

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
   <td colname="col03">作業階段 <p>第一列 </p></td> 
   <td colname="col3"> 訪客從指名搜尋引擎搜尋時，訪客作業中的第一個搜尋引擎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 下一個URI </td> 
   <td colname="col2"> 衍生（基於URI維的ShiftDim） </td> 
   <td colname="col03"> 頁面檢視 </td> 
   <td colname="col3"> 當前選定URI之後下一個URI的URI。 此衍生維度用於分析訪客在任何指定URI後接下來會執行什麼動作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 一次性與重複 </td> 
   <td colname="col2"> 衍生（根據重複訪客和一次性訪客量度的SegmentDim） </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 訪客類型：一次或重複。 一次性訪客在網站上只有一個作業，而重複訪客則有多個作業。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 頁面 </td> 
   <td colname="col2"> 派生（基於URI維的RenameDim） </td> 
   <td colname="col03"> 頁面檢視 </td> 
   <td colname="col3"> 作業期間瀏覽的每個頁面的名稱。 一開始，每個頁面的名稱與URI相同，但可以變更，以方便解讀。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 反向連結 </td> 
   <td colname="col2"> 繼承自內建反向連結維度 </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 先將工作階段轉介至網站之網站的第二層網域名稱（由訪客的瀏覽器提供）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜尋片語 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03">作業階段 <p>第一列 </p></td> 
   <td colname="col3"> 訪客從指名搜尋引擎搜尋時，搜尋引擎所傳遞之訪客作業中的第一個搜尋片語。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜尋詞 </td> 
   <td colname="col2"> 多對多 </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 當訪客有來自命名搜尋引擎的搜尋反向連結點進時，搜尋引擎傳遞的每個搜尋詞。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段持續時間 </td> 
   <td colname="col2"> 衍生（根據「精確頁面持續時間」度量的MetricDim） </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 以30秒為增量的作業持續時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 會話編號 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 訪客瀏覽網站的次數。 例如，首次訪客的作業數為"1"，第二次訪客的作業數為"2"等。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 作業頁面檢視 </td> 
   <td colname="col2"> 衍生（基於頁面檢視的MetricDim量度） </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 作業中的頁面檢視次數。 例如，在「作業頁面檢視」維度中選取「3」，將會選取具有3個頁面檢視的所有作業。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 搜尋引擎 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 第一個網站的二級網域名稱，此網站是指名的搜尋引擎，會在工作階段期間（由訪客的瀏覽器提供）將訪客引薦至網站。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間維度 </td> 
   <td colname="col2"> 簡單 </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 工作階段開始的小時、日、小時、小時、周、星期、月、季或年。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間報表維度 </td> 
   <td colname="col2"> 衍生（根據內建時間維度重新命名維度） </td> 
   <td colname="col03"> 作業階段 </td> 
   <td colname="col3"> 維度包括天前、上個月的天、上週的天、本月的天、本週的天、今天的小時、昨天的小時、過去12個月、過去2個月、過去2週、過去24小時、最近3個月、最近4週、最近6個月、過去7天，過去7天和今天，過去8週，過去9個月，上個月，上週，幾個月前，本月，本週，這和過去14天，這和過去6個月，這和過去8週，今天，今天，今天，今天，今天和過去30天，「前」和「昨天」提供建立工作區或報表的便利方式，一律會顯示資料集中的部分資料。 每項作業都以作業開始時為基礎。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI </td> 
   <td colname="col2"> 繼承自內建維URI </td> 
   <td colname="col03"> 頁面檢視 </td> 
   <td colname="col3"> 每個已檢視頁面的URI。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客頁面檢視 </td> 
   <td colname="col2"> 衍生（基於頁面檢視的MetricDim量度） </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 訪客目前的頁面檢視次數。 例如，在「訪客頁面檢視」維度中選取「3」，將會選取所有工作階段中具有3個頁面檢視的所有訪客。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪客反向連結 </td> 
   <td colname="col2"> 繼承自內建維度「反向連結」 </td> 
   <td colname="col03"> 訪客 </td> 
   <td colname="col3"> 首次將訪客引薦至網站進行其第一個工作階段（由訪客的瀏覽器提供）之網站的第二層網域名稱。 </td> 
  </tr> 
 </tbody> 
</table>

