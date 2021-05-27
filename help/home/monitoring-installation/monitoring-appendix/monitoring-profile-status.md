---
description: 下列維度可用於Data Workbench的「設定檔狀態」設定檔。
title: Data Workbench 設定檔狀態設定檔中的維度
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Data Workbench 設定檔狀態設定檔中的維度{#dimensions-in-the-data-workbench-profile-status-profile}

下列維度可用於Data Workbench的「設定檔狀態」設定檔。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>區塊</b> </td> 
   <td colname="col2"> 這是此設定中唯一可計數的，且以根存在於所有維度。 區塊可視為伺服器。 它使用x-trackingid欄位。 區塊ID是伺服器名稱加主機名稱的雜湊，因此每個設定檔的每個伺服器大約會有一個區塊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延遲分鐘數</b> </td> 
   <td colname="col2"> cs-uri-query(bi)會放入x-as-of-delay-minutes欄位中，並捨入至最接近的分鐘數。 「截止延遲分鐘數」是數值維度，會將區塊的「最後一列」從x-as-of-delay-minutes取得。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2"> cs-uri-query(c)值用於環境ID。 區塊的最後一列會作為維度的值。 此「簡單」Dimension將顯示您的伺服器正在運行的環境（如果配置正確）。 <p>這可在insight_monitor_agent.cfg檔案中設定 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速輸入MegaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值用於此維度。 區塊的最後一列會作為維度的值。 如果資料集為「快速輸入」，此數值Dimension的值將顯示系統輸入資料時的每分鐘MB。 <p>注意： 此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速合併MegaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用於此維度。 區塊的最後一列會作為維度的值。 如果資料集處於快速合併中此數值Dimension的值將顯示系統每分鐘合併的MB。 <p>注意： 此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>欄位GigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bg)值用於此維度。 此值除以1000，並四捨五入至最接近的整數。 此數值Dimension的值會顯示資料集中欄位所使用的空間量。 <p>注意： 此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主機</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用於此維度。 簡單維的值是塊的最後一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping</b> </td> 
   <td colname="col2">x-last-ping是x-unixtime除以10（以符合數值維度大小限制）。 Last Ping是指定塊的最後一行，它代表監視代理上次記錄系統運行狀況的時間。 <p>注意： 此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日誌讀取百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值用於此數值維度。 這是指定區塊的最後一列。 此維度用於計算讀取的記錄檔百分比。 <p>注意： 此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用於此簡單Dimension。 這是指定區塊的最後一列。 處理模式ID允許您查看系統處於何種處理模式（快速輸入、快速合併、即時）。 <p>注意： 此維度會隱藏，然後在用戶端維度處理模式中以好記的值重新公開。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理已中止</b> </td> 
   <td colname="col2"> 已x處理中止欄位會透過各種條件建立，以指出設定檔目前是否執行中。 這是一個簡單的維度。 <p>注意： 當有大量輸入記錄要公平分佈在DPU中時，此維度的效用最佳。 舉例來說，如果每天只載入一個大型檔案，則Data Workbench可能會「停頓」一小時或更久，導致此維度的誤判。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>設定檔</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用於此簡單Dimension。 此維度會顯示目前監控之設定檔的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>源最後</b> </td> 
   <td colname="col2"> cs-uri-query(bl)的最後一行被複製到x-source-emestive-bidfin欄位中。 簡單Dimension使用給定塊的最後一行。 此維度會顯示上次與資料來源聯絡的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轉換百分比</b> </td> 
   <td colname="col2"> cs-uri-query(bf)值用於此數值維度。 這是指定區塊的最後一列。 此維度用於計算完成資料轉換的百分比。 <p>注意： 此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>時間維度</b> </td> 
   <td colname="col2"> 小時、日、周、月、小時和星期都衍生自x-timestamp欄位。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群組</b> </td> 
   <td colname="col2"> 將字詞分組，可讓您透過其他方式篩選產生的資料集。 在insight_monitor_agent.cfg檔案中設定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>量度</b> </td> 
   <td colname="col2"> 下表列出Data Workbench設定檔監控設定檔中包含的量度，以及其衍生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延遲分鐘數</b> </td> 
   <td colname="col2"> 此量度是每個區塊的「截止延遲分鐘數」總和，然後除以「區塊」量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延遲秒數</b> </td> 
   <td colname="col2"> 此度量是每個塊的「截止延遲秒數」的總和，除以塊總數。 (從延遲秒數開始Dimension未立即配置) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>區塊</b> </td> 
   <td colname="col2"> 每個塊加總一個。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速輸入MB</b> </td> 
   <td colname="col2"> 當每分鐘快速輸入MegaBytes大於零時，每個塊的快速輸入MegaBytes/Minute總和除以塊數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速合併MB</b> </td> 
   <td colname="col2"> 每個塊的「快速合併兆位元組數」除以每分鐘的「快速合併兆位元組數」大於零時的塊數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>欄位GigaBytes</b> </td> 
   <td colname="col2"> 每個塊除以塊度量的欄位GB總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping年齡</b> </td> 
   <td colname="col2"> 截止時間減去上次Ping時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping時間</b> </td> 
   <td colname="col2"> 每個塊的Last Ping總和除以Blocks，然後乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日誌讀取</b> </td> 
   <td colname="col2"> 其中Log Reading Percentage大於零，Log Reading是每個塊的Log Reading Percentage的總和，除以Blocks度量，所有塊除以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理已中止</b> </td> 
   <td colname="col2"> 每個區塊的「處理中止」Dimension總和，除以「區塊」量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轉換</b> </td> 
   <td colname="col2"> 每個塊的「轉換百分比」除以「塊」度量的總和，當「轉換百分比」大於零時，全部除以10。 </td> 
  </tr> 
 </tbody> 
</table>
