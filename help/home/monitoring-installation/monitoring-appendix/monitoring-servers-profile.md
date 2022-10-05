---
description: 下列維度可在Data Workbench的「伺服器狀態」設定檔中使用。
title: Data Workbench 伺服器狀態設定檔中的維度
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Data Workbench 伺服器狀態設定檔中的維度{#dimensions-in-the-data-workbench-server-status-profile}

{{eol}}

下列維度可在Data Workbench的「伺服器狀態」設定檔中使用。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>伺服器</b> </td> 
   <td colname="col2"> 此可數維度是從x-trackingid欄位建立，代表目前執行Data Workbench的伺服器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>代理版本</b> </td> 
   <td colname="col2"> cs-uri-query(af)值用於此簡單Dimension。 這是伺服器的最後一個非空白值。 這會顯示執行中監控代理的版本的建立日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何設定檔重新處理</b> </td> 
   <td colname="col2"> cs-uri-query(aa)欄位用於此數值Dimension，它是給定伺服器的「最後一行」的值，條件是cs-uri-query(k)不為空。 此維度用於指出是否有任何設定檔正在重新處理。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>能力行百分比</b> </td> 
   <td colname="col2"> cs-uri-query(r)欄位用於此數值Dimension，它是給定伺服器的「最後一行」的值，條件是cs-uri-query(k)不為空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> cs-uri-query(n)欄位用於此數值Dimension，它是給定伺服器的「最後一行」的值，條件是cs-uri-query(k)不為空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>公用名稱</b> </td> 
   <td colname="col2"> sc-ur-query(am)欄位用於此簡單Dimension，它是給定伺服器的Last Nonblank值的值。 它顯示被監視的伺服器的公用名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>元件檢查成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)欄位用於此簡單Dimension，它是給定伺服器的最後一行的值。 此維度會檢查伺服器的元件，以確認其是否正常運作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出錯的元件</b> </td> 
   <td colname="col2"> Crossrows轉換會取用cs-uri-query(ao)的Last Row值，並將其複製到x-components-in-error欄位中。 此「多對多」維度在正在監控的伺服器上顯示任何出錯的元件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2">cs-uri-query(c)值用於環境ID。 區塊的最後一列會作為維度的值。 此「簡單」Dimension將顯示您的伺服器正在運行的環境（如果配置正確）。 <p><p>注意：此維度設定在insight_monitor_agent.cfg中。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估計掃描秒數</b> </td> 
   <td colname="col2"> 此「數值」Dimension中使用x-estimated-sweep-dekasseconds欄位。 這是伺服器的估計掃描時間除以10（減小掃描測量的解析度以使尺寸更合理）。 <p><p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主機</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用於此維度。 簡單維的值是塊的最後一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping</b> </td> 
   <td colname="col2"> x-last-ping是x-unixtime除以10（以符合數值維度大小限制）。 Last Ping是指定塊的最後一行，它代表監視代理上次記錄系統運行狀況的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>載入平均</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(i)值的最後一行的數值維。 條件是cs-uri-query(k)不為空。 此維度用於計算所監視系統中伺服器的平均負載。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體頁檔案百分比</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(o)值的最後一行的數值維。 條件是cs-uri-query(k)不為空。 此維度用於計算頁面檔案記憶體使用量的百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理兆位元組總數</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(ag)值的最後一行的數值維。 條件是cs-uri-query(k)不為空。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理百分比</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(ag)值的最後一行的數值維。 條件是cs-uri-query(k)不為空。 此維度用於計算每個伺服器的物理記憶體使用率百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體查詢百分比</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query值的最後一行的數值維。 條件是cs-uri-query(k)不為空。 此維度用於計算每個伺服器的查詢記憶體使用率百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>網路連接</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(q)值的最後一行的數值維。 條件是cs-uri-query(k)不為空。 這用於顯示指定伺服器的網路連接數。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輪詢延遲（秒）</b> </td> 
   <td colname="col2"> 此維度用於計算民調問答延遲。 cs-uri-query(m)值除以10以縮小維度大小，並複製到x-poll-latency-centiseconds欄位中。 這是數值維度，會取用指定伺服器的最後一列。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查成功</b> </td> 
   <td colname="col2"> 這是從給定伺服器的最後一行的cs-uri-query(g)值構建的簡單維。 用於計算快速檢查量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>臨時DB空間百分比</b> </td> 
   <td colname="col2"> cs-uri-query(an)值的最後一行被複製到x-temp-db-space-percentage欄位中。 這是數值Dimension，用於計算指定伺服器上已用臨時資料庫空間的百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>分析版本</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用於此簡單Dimension。 這是伺服器的最後一個非空白值。 這會顯示每個伺服器上執行的Data Workbench伺服器版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群組</b> </td> 
   <td colname="col2"> 將字詞分組，可讓您透過其他方式篩選產生的資料集。 <p>注意：此維度設定在insight_monitor_agent.cfg中。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>量度</b> </td> 
   <td colname="col2"> 下表列出Data Workbench設定檔監控設定檔中包含的量度，以及其衍生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>總容量</b> </td> 
   <td colname="col2"> 這是容量大小度量乘以2加上容量行度量除以3。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行</b> </td> 
   <td colname="col2"> 這是每個伺服器的容量行百分比除以伺服器量度的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小</b> </td> 
   <td colname="col2"> 這是每個伺服器的容量大小百分比除以伺服器量度的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>元件檢查</b> </td> 
   <td colname="col2"> 這是「元件檢查成功等於1」的伺服器數，除以「服務為DPU或FSU的伺服器」，再加上100（以成為百分比）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁碟"x"</b> </td> 
   <td colname="col2"> 「磁碟」度量的計算方式是取每個伺服器的「磁碟使用百分比」除以「伺服器」度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估計掃描分鐘數</b> </td> 
   <td colname="col2"> 這是每個伺服器的「估計掃描秒數」除以「伺服器」度量的總和，其中「估計掃描秒數」大於零，全部除以6。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping時間</b> </td> 
   <td colname="col2"> 每個塊的Last Ping總和除以Blocks，然後乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>載入</b> </td> 
   <td colname="col2"> 這是每個伺服器的「負載平均」除以「伺服器」量度的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體頁檔案</b> </td> 
   <td colname="col2"> 這是每個伺服器的記憶體頁面檔案百分比除以伺服器量度的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理</b> </td> 
   <td colname="col2"> 這是每台伺服器的記憶體物理百分比除以伺服器度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體查詢</b> </td> 
   <td colname="col2"> 這是每個伺服器的記憶體查詢百分比除以伺服器量度的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>網路連接</b> </td> 
   <td colname="col2"> 這是每個伺服器的網路連接數除以「伺服器」度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輪詢延遲毫秒</b> </td> 
   <td colname="col2"> 這是每個伺服器的輪詢延遲秒數加以伺服器量度的總和，所有量度均乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查</b> </td> 
   <td colname="col2"> 這是「快速檢查成功」等於1的伺服器數，除以「伺服器」量度，再乘以100。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>伺服器</b> </td> 
   <td colname="col2"> 這是每個伺服器的1的總和，或受監視的伺服器的總數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>臨時DB</b> </td> 
   <td colname="col2"> 這是每個伺服器的臨時資料庫空間百分比除以「伺服器」度量的總和。 </td> 
  </tr> 
 </tbody> 
</table>
