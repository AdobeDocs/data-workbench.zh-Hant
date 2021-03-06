---
description: 行銷您的網站可能涉及在第三方網站上以影像或其他多媒體檔案（從您的網站伺服器提供）的形式放置廣告。
title: 測量廣告曝光次數
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# 測量廣告曝光次數{#measuring-advertisement-impression}

行銷您的網站可能涉及在第三方網站上以影像或其他多媒體檔案（從您的網站伺服器提供）的形式放置廣告。

在這種情況下，您可能會想要測量廣告在瀏覽器上的曝光次數，以及後續的點進次數（如果有的話），以測量您網站上廣告的目標URL。

對於以影像形式的廣告，將[!DNL Log=1]附加到查詢字串會導致影像請求，從而導致廣告曝光，由[!DNL Sensor]用於分析目的捕獲。

```
<!—REFERENCE IMPRESSION TAG->
<IMG SRC="https://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=https://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_ic= | 表示曝光促銷活動的值 | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | 表示曝光促銷活動資產的值 | v_ica=」72890ab」 |
| v_icr= | 表示曝光促銷活動反向連結的值 | v_icr=」https://money.cnn.com/markets/ |

除了將[!DNL Log=1]附加至影像要求之外，還應將識別碼新增至從廣告導向至網站內目標頁面的URL，以追蹤導致點進的廣告，並追蹤點進回該廣告的特定促銷活動。

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=https://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 收集的資料 </th>
   <th colname="col2" class="entry"> 解釋 </th>
   <th colname="col3" class="entry"> 範例 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> v_c= </td>
   <td colname="col2"> 表示點進促銷活動的值 </td>
   <td colname="col3"> v_c=」CAMPAIGN1」 </td>
  </tr>
  <tr>
   <td colname="col1"> v_ca= </td>
   <td colname="col2"> 表示點進促銷活動資產的值 </td>
   <td colname="col3"> v_ca=」72890ab」 </td>
  </tr>
  <tr>
   <td colname="col1"> v_cr= </td>
   <td colname="col2"> 表示點進促銷活動反向連結的值 </td>
   <td colname="col3"> <p> <span class="filepath"> v_cr=」https://money.cnn.com/</span> </p> <p>市場/ </p> </td>
  </tr>
 </tbody>
</table>
