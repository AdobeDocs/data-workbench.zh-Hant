---
description: 以下維度可用於資料工作台歷史設定檔。
title: Data Workbench 歷史設定檔中的維度
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Data Workbench 歷史設定檔中的維度{#dimensions-in-the-data-workbench-historic-profile}

以下維度可用於資料工作台歷史設定檔。

## Data Workbench 歷史設定檔中的維度 {#section-96f1b64f5cb84411b630f97f227d888d}

以下維度可用於資料工作台歷史設定檔。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>區塊</b> </td> 
   <td colname="col2">這是此組態中唯一可計數的，是所有維的根。 塊可以被視為伺服器。 它使用x-trackingid欄位。 <p>注意： 區塊ID是伺服器名稱加上主機名稱的雜湊，因此每個描述檔每個伺服器大約會有一個區塊。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> 這是由塊可計數構成的可計數維。 配置檔案中的每一行資料都是來自監視代理的ping。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>緊急警報</b> </td> 
   <td colname="col2"> 從cs-uri-query(ad)值建立數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警報關閉</b> </td> 
   <td colname="col2"> 以cs-uri-query(ac)值建立的數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警報警告</b> </td> 
   <td colname="col2"> 從cs-uri-query(ae)值建立數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何描述檔重新處理</b> </td> 
   <td colname="col2"> 從cs-uri-query(aa)值建立數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"，而cs-uriquery(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延遲分鐘數</b> </td> 
   <td colname="col2"> cs-uri-query(bi)會放入x-as-of-delay-minutes欄位，並捨入至最接近的分鐘。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>能力行百分比</b> </td> 
   <td colname="col2"> 從cs-uri-query(r)值建立數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"，而cs-uriquery(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> 從cs-uri-query(n)值建立數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"，而cs-uriquery(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>元件檢查成功</b> </td> 
   <td colname="col2"> 從cs-uri-query(v)值建立的簡單Dimension。 它是在Ping層級建立，並以cs-uri-query(a)符合"1"為條件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>發生錯誤的元件</b> </td> 
   <td colname="col2"> cs-uri-query(ao)由"|"分隔字元分割，並複製至x-components-in-error欄位。 從x-components-in-error欄位建立的「多對多」Dimension。 在Ping級別構建。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細檢查秒數</b> </td> 
   <td colname="col2"> 從cs-uri-query(l)值建立數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細檢查成功</b> </td> 
   <td colname="col2"> 從cs-uri-query(k)值建立的簡單Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DimensionGigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc)會複製至x-dimension-gigbs欄位。 x-dimension-gigbats欄位是此簡單Dimension的使用者，以cs-uri-query(a)符合"2"為條件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁碟"x"已用百分比</b> </td> 
   <td colname="col2"> 這些數值Dimension是從cs-uri-query(ah, ai, aj, ak, al)值設定。 它們是在Ping層級建立，並以cs-uri-query(a)符合"1"而cs-uri-query(k)非空白為條件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估計掃描秒數</b> </td> 
   <td colname="col2"> x-estimated-sweep-dekassends欄位用於此數值Dimension。 這是估計的伺服器掃描時間除以10（降低掃描測量的解析度，以使尺寸更合理地調整）。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速輸入MegaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值用於此維度。 塊的最後一行用作維的值。 如果資料集在「快速輸入」中，此數值Dimension的值將顯示系統輸入資料時的每分鐘MB。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速合併MegaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用於此維度。 塊的最後一行用作維的值。 如果資料集在快速合併中此數值Dimension的值將顯示系統合併時的每分鐘MB。 <p><p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>欄位千兆位元組</b> </td> 
   <td colname="col2">cs-uri-query(bg)值用於此維度。 此值除以1000，並捨入至最接近的整數。 此數值Dimension的值將顯示資料集中欄位使用的空間量。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群組</b> </td> 
   <td colname="col2"> 從cs-uri-query(x)值在Ping層級建立簡單Dimension。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主機</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用於此維度。 「簡單」維的值是塊的最後一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping</b> </td> 
   <td colname="col2"> x-unixtime欄位會複製為x-last-ping，並除以10，以降低基數。 數值Dimension是在塊級別構建的，使用x-last-ping欄位。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>載入平均值</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(i)值之最後一列的數值維度。 其條件是cs-uri-query(k)不是空的。 此維用於計算所監視系統中伺服器的平均負載。 <p><p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日誌讀取百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值用於此數值維度，建立在Ping層級。 此維用於計算正在讀取的日誌的百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體頁檔案百分比</b> </td> 
   <td colname="col2"> 這是使用cs-uri-query(o)值的數值維度，建立在Ping層級。 其條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合"1"。 此維度用來計算頁面檔案記憶體使用百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理MegaBytes總計</b> </td> 
   <td colname="col2">這是使用cs-uri-query(ag)值的數值維度，建立在Ping層級。 其條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合"1"。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理百分比</b> </td> 
   <td colname="col2">這是使用cs-uri-query(ag)值的數值維度，建立在Ping層級。 其條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合"1"。 此維度用於計算每個伺服器的物理記憶體使用百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體查詢百分比</b> </td> 
   <td colname="col2"> 這是使用Ping層級cs-uri-query值的數值維度。 其條件是cs-uri-query(k)不為空，cs-uri-query(a)符合"1"。 此維度用於計算每個伺服器的查詢記憶體使用百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>網路連接</b> </td> 
   <td colname="col2"> 這是使用在Ping層級建立之cs-uri-query(q)值的數值維度。 其條件是cs-uri-query(k)不為空，cs-uri-query(a)符合"1"。 它用於顯示給定伺服器的網路連接數。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輸出行</b> </td> 
   <td colname="col2"> cs-uri-query(bh)值除以100000，並複製到x-output-rows欄位，以減小維度的大小。 X-output-rows用於在Ping層級建立的數值Dimension，條件是cs-uri-query(a)符合"2"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping類型ID</b> </td> 
   <td colname="col2"> 使用cs-uri-query(a)值在Ping層級建立簡單Dimension。 顯示錄制的Ping類型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輪詢延遲不等於秒</b> </td> 
   <td colname="col2">cs-uri-query(m)值除以10以減少維度大小，並複製至x-poll-latency-centiseconds欄位。 這是在Ping層級建立的數值維度，條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合"1"/此維度用於計算民調問答延遲。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用於此簡單Dimension，建立於Ping層級。 條件是cs-uri-query(bb)不是空的，而cs-uri-query(a)符合「2」處理模式ID，讓您可檢視系統處於何種處理模式（快速輸入、快速合併、即時）。 <p>注意： 此維度會隱藏，然後在用戶端維度處理模式中以友好值重新顯示。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>設定檔</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用於此簡單Dimension，它是在Ping級別構建的。 此維顯示當前受監視的配置檔案的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查秒數</b> </td> 
   <td colname="col2"> cs-uri-query(h)值用於此數值Dimension。 它是在Ping層級建立，條件是cs-uri-query(a)符合"1"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查成功</b> </td> 
   <td colname="col2"> 這是從cs-uri-query(g)值建立在Ping層級的「簡單」維度。 它用於計算快速檢查度量。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>即時處理百分比</b> </td> 
   <td colname="col2"> 使用在Ping層級建立的cs-uri-query(t)值進行數值Dimension。 cs-uri-query(a)符合"1"的條件。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>最遠的來源</b> </td> 
   <td colname="col2"> 從cs-uri-query(bl)值建立的簡單Dimension，在Ping層級建立。 此維度會顯示上次與資料來源的連絡發生的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>臨時資料庫空間百分比</b> </td> 
   <td colname="col2">使用cs-uri-query(an)值建立的數值Dimension，在Ping層級建立。 條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合"1"。 它用於計算給定伺服器上已用臨時資料庫空間的百分比。 <p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轉換百分比</b> </td> 
   <td colname="col2">cs-uri-query(bf)值用於此數值維度。 它是在Ping級別構建的。 此維度用於計算完成資料轉換的百分比。 <p><p>注意： 此維度會隱藏，因為只有在平均成為度量時，它才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用於此簡單Dimension。 它建立在Ping層級，並且條件是cs-uri-query(ab)不為空，而cs-uri-query(a)符合"1"。 這會顯示每個伺服器上執行的資料工作台伺服器版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版主修</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值會被分割，而主要發行值會複製到x-insight-version-major欄位中。 它是在Ping層級建立的簡單Dimension，並且條件是x-insight-version-major不是空的，且cs-uri-query(a)符合"1"。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
