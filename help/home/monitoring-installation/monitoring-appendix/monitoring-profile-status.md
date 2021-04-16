---
description: 以下維可用於資料工作台配置檔案狀態配置檔案。
title: Data Workbench 設定檔狀態設定檔中的維度
uuid: bd84a3e5-d1ea-4768-9dac-62f5dfbad49a
exl-id: 57b3ff16-26db-4292-819b-f6cd8e024c2a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 2%

---

# Data Workbench 設定檔狀態設定檔中的維度{#dimensions-in-the-data-workbench-profile-status-profile}

以下維可用於資料工作台配置檔案狀態配置檔案。

<table id="table_DD143B4F15FF446DAD24BD2473B485B9"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>區塊</b> </td> 
   <td colname="col2"> 這是此配置中唯一的可計數，並作為所有維的根存在。 塊可以被視為伺服器。 它使用x-trackingid欄位。 區塊ID是伺服器名稱加上主機名稱的雜湊，因此每個描述檔每個伺服器大約會有一個區塊。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延遲分鐘數</b> </td> 
   <td colname="col2"> cs-uri-query(bi)會放入x-as-of-delay-minutes欄位，並捨入至最接近的分鐘。 「截止延遲分鐘」是數值維，它將塊的「最後一行」從x-as-of-delay-minutes中取代。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2"> cs-uri-query(c)值用於環境ID。 塊的最後一行用作維的值。 此簡單Dimension將顯示伺服器正在運行的環境（如果配置正確）。 <p>這可在insight_monitor_agent.cfg檔案中設定 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速輸入MegaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值用於此維度。 塊的最後一行用作維的值。 如果資料集在「快速輸入」中，此數值Dimension的值將顯示系統輸入資料時的每分鐘MB。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速合併MegaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用於此維度。 塊的最後一行用作維的值。 如果資料集在快速合併中此數值Dimension的值將顯示系統合併時的每分鐘MB。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>欄位千兆位元組</b> </td> 
   <td colname="col2"> cs-uri-query(bg)值用於此維度。 此值除以1000，並捨入至最接近的整數。 此數值Dimension的值將顯示資料集中欄位使用的空間量。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主機</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用於此維度。 「簡單」維的值是塊的最後一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping</b> </td> 
   <td colname="col2">x-last-ping是x-unixtime除以10（以符合數值維度大小限制）。 Last Ping是指定塊的最後一行，它代表監視代理上次記錄系統運行狀況的時間。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日誌讀取百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值會用於此數值維度。 這是給定塊的最後一行。 此維用於計算正在讀取的日誌的百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用於此簡單Dimension。 它是給定區塊的最後一列。 處理模式ID可讓您查看系統處理模式（快速輸入、快速合併、即時）。 <p>注意： 此維度會隱藏，然後在用戶端維度處理模式中以友好值重新顯示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理停止</b> </td> 
   <td colname="col2"> x-processing-stalted欄位是通過各種條件建立的，以指示配置檔案當前是否正在運行。 它是一個簡單的維度。 <p>注意： 當有許多輸入記錄檔要在DPU之間公平分佈時，此維度最適合。 例如，如果每天僅載入一個大型檔案，則資料工作台可能會「停止」一小時或多小時，導致從此維度讀取錯誤正數。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>設定檔</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用於此簡單Dimension。 此維顯示當前受監視的配置檔案的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最遠的來源</b> </td> 
   <td colname="col2"> cs-uri-query(bl)的最後一列被複製到x-source-emlest-boind欄位中。 簡單Dimension使用給定塊的最後一行。 此維度會顯示上次與資料來源的連絡發生的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轉換百分比</b> </td> 
   <td colname="col2"> cs-uri-query(bf)值用於此數值維度。 這是給定塊的最後一行。 此維度用於計算完成資料轉換的百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>時間維度</b> </td> 
   <td colname="col2"> 小時、日、周、月、小時和週日均衍生自x-timestamp欄位。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群組</b> </td> 
   <td colname="col2"> 將字詞分組，提供您另一種篩選產生資料集的方式。 在insight_monitor_agent.cfg檔案中設定。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>量度</b> </td> 
   <td colname="col2"> 以下列出資料工作台描述檔監控描述檔中包含的量度，以及其衍生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延遲分鐘</b> </td> 
   <td colname="col2"> 此度量是每個區塊的「截止延遲分鐘數」的總和，再除以「區塊」度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>從延遲秒數開始</b> </td> 
   <td colname="col2"> 此度量是每個區塊的「延遲秒數截止」的總和，除以區塊總數。 (從「延遲秒數」Dimension開始，未在出廠時配置) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>塊</b> </td> 
   <td colname="col2"> 對每個塊求和一個。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速輸入MB</b> </td> 
   <td colname="col2"> 每個塊的快速輸入MegaBytes/Minute總和除以「快速輸入MegaBytes/Minute」大於零時的塊數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速合併MB</b> </td> 
   <td colname="col2"> 每個塊的「快速合併兆位元組」的總和除以「每分鐘快速合併兆位元組」大於零時的塊數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>欄位千兆位元組</b> </td> 
   <td colname="col2"> 每個塊的欄位GB總和除以塊度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping年齡</b> </td> 
   <td colname="col2"> 截止時間減去上次Ping時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping時間</b> </td> 
   <td colname="col2"> 每個塊的「最後Ping」總和除以「塊」，再乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日誌讀取</b> </td> 
   <td colname="col2"> 其中，「日誌讀取百分比」大於零，「日誌讀取」是每個塊的「日誌讀取百分比」除以「塊」度量的總和，所有塊除以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理停止</b> </td> 
   <td colname="col2"> 每個塊的「處理停止Dimension」總和除以「塊」度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轉換</b> </td> 
   <td colname="col2"> 當「轉換百分比」大於零時，每個塊的「轉換百分比」除以「塊」度量的總和，全部除以10。 </td> 
  </tr> 
 </tbody> 
</table>
