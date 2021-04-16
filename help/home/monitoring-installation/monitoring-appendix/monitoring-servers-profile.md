---
description: 以下維可用於資料工作台的「伺服器狀態」配置檔案。
title: Data Workbench 伺服器狀態設定檔中的維度
uuid: 4cfe882a-2797-4af9-bd6d-75bc31ee909c
exl-id: 002f6b95-f151-41d9-ae28-9c01c1f621ee
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1366'
ht-degree: 1%

---

# Data Workbench 伺服器狀態設定檔中的維度{#dimensions-in-the-data-workbench-server-status-profile}

以下維可用於資料工作台的「伺服器狀態」配置檔案。

<table id="table_10DFAD7A0C5946B0A2458F6C08D04FC5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>伺服器</b> </td> 
   <td colname="col2"> 此可計數維度是從x-trackingid欄位建立，代表目前執行資料工作台的伺服器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>代理版本</b> </td> 
   <td colname="col2"> cs-uri-query(af)值用於此簡單Dimension。 這是伺服器的「最後一個非空值」。 這將顯示運行的監視代理版本的構建日期和時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何描述檔重新處理</b> </td> 
   <td colname="col2"> cs-uri-query(aa)欄位用於此數值Dimension，它是指定伺服器的「最後一列」值，條件是cs-uri-query(k)不是空的。 此維用於指示是否正在重新處理任何配置檔案。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>能力行百分比</b> </td> 
   <td colname="col2"> cs-uri-query(r)欄位用於此數值Dimension，它是指定伺服器的「最後一列」的值，條件是cs-uri-query(k)不為空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> cs-uri-query(n)欄位用於此數值Dimension，它是指定伺服器的「最後一列」值，條件是cs-uri-query(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>通用名稱</b> </td> 
   <td colname="col2"> sc-ur-query(am)欄位用於此簡單Dimension，它是給定伺服器的「最後一個非空白」值的值。 它顯示所監視伺服器的「通用名稱」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>元件檢查成功</b> </td> 
   <td colname="col2"> cs-uri-query(v)欄位用於此簡單Dimension，它是指定伺服器的最後一列值。 此維度會檢查伺服器的元件，以確認它們是否正常運作。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>發生錯誤的元件</b> </td> 
   <td colname="col2"> Crossrows轉換會取用cs-uri-query(ao)的「最後一列」值，並將其複製到x-components-in-error欄位。 此「多到多」維在所監視的伺服器上顯示任何出錯的元件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>環境</b> </td> 
   <td colname="col2">cs-uri-query(c)值用於環境ID。 塊的最後一行用作維的值。 此簡單Dimension將顯示伺服器正在運行的環境（如果配置正確）。 <p><p>注意： 此維度是在insight_monitor_agent.cfg中設定。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估計掃描秒數</b> </td> 
   <td colname="col2"> x-estimated-sweep-dekassends欄位用於此數值Dimension。 這是估計的伺服器掃描時間除以10（降低掃描測量的解析度，以使尺寸更合理地調整）。 <p><p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主機</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用於此維度。 「簡單」維的值是塊的最後一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping</b> </td> 
   <td colname="col2"> x-last-ping是x-unixtime除以10（以符合數值維度大小限制）。 Last Ping是指定塊的最後一行，它代表監視代理上次記錄系統運行狀況的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>載入平均值</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(i)值之最後一列的數值維度。 其條件是cs-uri-query(k)不是空的。 此維用於計算所監視系統中伺服器的平均負載。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體頁檔案百分比</b> </td> 
   <td colname="col2"> 這是使用指定伺服器cs-uri-query(o)值之最後一列的數值維度。 其條件是cs-uri-query(k)不是空的。 此維度用來計算頁面檔案記憶體使用百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理MegaBytes總計</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(ag)值之最後一列的數值維度。 其條件是cs-uri-query(k)不是空的。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理百分比</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(ag)值之最後一列的數值維度。 其條件是cs-uri-query(k)不是空的。 此維度用於計算每個伺服器的物理記憶體使用百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體查詢百分比</b> </td> 
   <td colname="col2"> 這是使用指定伺服器cs-uri-query值之最後一列的數值維度。 其條件是cs-uri-query(k)不是空的。 此維度用於計算每個伺服器的查詢記憶體使用百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>網路連接</b> </td> 
   <td colname="col2"> 這是使用指定伺服器cs-uri-query(q)值之最後一列的數值維度。 其條件是cs-uri-query(k)不是空的。 它用於顯示給定伺服器的網路連接數。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輪詢延遲不等於秒</b> </td> 
   <td colname="col2"> 此維度用來計算民調問答延遲。 cs-uri-query(m)值除以10以減少維度大小，並複製至x-poll-latency-centiseconds欄位。 這是數值維度，會取得指定伺服器的最後一列。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查成功</b> </td> 
   <td colname="col2"> 這是從指定伺服器的「最後一列」的cs-uri-query(g)值建立的簡單維度。 它用於計算快速檢查度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>臨時資料庫空間百分比</b> </td> 
   <td colname="col2"> cs-uri-query(an)值的最後一行會複製到x-temp-db-space-percentage欄位。 此為數值Dimension，用於計算給定伺服器上已用臨時資料庫空間的百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Insight版本</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用於此簡單Dimension。 這是伺服器的「最後一個非空值」。 這會顯示每個伺服器上執行的資料工作台伺服器版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群組</b> </td> 
   <td colname="col2"> 將字詞分組，提供您另一種篩選產生資料集的方式。 <p>注意： 此維度是在insight_monitor_agent.cfg中設定。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>量度</b> </td> 
   <td colname="col2"> 以下列出資料工作台描述檔監控描述檔中包含的量度，以及其衍生方式。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>整體容量</b> </td> 
   <td colname="col2"> 這是「容量大小」度量乘以2，再加上「容量行」度量除以3。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量行</b> </td> 
   <td colname="col2"> 這是每個伺服器的容量行百分比除以伺服器度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小</b> </td> 
   <td colname="col2"> 這是每個伺服器的容量大小百分比除以伺服器度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>元件檢查</b> </td> 
   <td colname="col2"> 這是「元件檢查成功」等於1的伺服器數，除以「服務」為DPU或FSU的伺服器，再乘以100（以使其為百分比）。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁碟"x"</b> </td> 
   <td colname="col2"> 「磁碟」度量的計算方式是取每個伺服器的「磁碟使用百分比」除以「伺服器」度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估計掃描分鐘數</b> </td> 
   <td colname="col2"> 這是每個伺服器的「估計掃描秒數」除以「估計掃描秒數」大於零的「伺服器」度量（全部除以6）的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping時間</b> </td> 
   <td colname="col2"> 每個塊的「最後Ping」總和除以「塊」，再乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>載入</b> </td> 
   <td colname="col2"> 這是每個伺服器的「平均負載」除以「伺服器」度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體頁面檔案</b> </td> 
   <td colname="col2"> 這是每個伺服器的記憶體頁檔案百分比除以伺服器度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>物理記憶體</b> </td> 
   <td colname="col2"> 這是每個伺服器的記憶體物理百分比除以伺服器度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體查詢</b> </td> 
   <td colname="col2"> 這是每個伺服器的記憶體查詢百分比除以伺服器度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>網路連接</b> </td> 
   <td colname="col2"> 這是每個伺服器的網路連接除以伺服器度量的總和。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輪詢延遲毫秒</b> </td> 
   <td colname="col2"> 這是每個伺服器的輪詢延遲等分秒數的總和，除以伺服器量度，所有量度都乘以10。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查</b> </td> 
   <td colname="col2"> 這是「快速檢查成功」等於1的「伺服器」數目，除以「伺服器」量度，再乘以100。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>伺服器</b> </td> 
   <td colname="col2"> 這是每個伺服器的總和，或受監視伺服器的總數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>臨時資料庫</b> </td> 
   <td colname="col2"> 這是每個伺服器的臨時資料庫空間百分比的總和，除以伺服器度量。 </td> 
  </tr> 
 </tbody> 
</table>
