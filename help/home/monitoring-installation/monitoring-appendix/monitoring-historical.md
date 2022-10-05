---
description: 下列維度可用於Data Workbench歷史設定檔。
title: Data Workbench 歷史設定檔中的維度
uuid: 6d93fba4-986b-46a4-9479-aeb54853dff5
exl-id: 9df1f317-a985-4132-b32e-f2263e0c23b2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1698'
ht-degree: 1%

---

# Data Workbench 歷史設定檔中的維度{#dimensions-in-the-data-workbench-historic-profile}

{{eol}}

下列維度可用於Data Workbench歷史設定檔。

## Data Workbench 歷史設定檔中的維度 {#section-96f1b64f5cb84411b630f97f227d888d}

下列維度可用於Data Workbench歷史設定檔。

<table id="table_3EAEA68E73BE431D841F7F2E83EDD6AC"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>區塊</b> </td> 
   <td colname="col2">這是此設定中唯一可計數的，是所有維的根。 區塊可視為伺服器。 它使用x-trackingid欄位。 <p>注意：區塊ID是伺服器名稱加主機名稱的雜湊，因此每個設定檔的每個伺服器大約會有一個區塊。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping</b> </td> 
   <td colname="col2"> 這是由塊可數構成的可數維。 設定檔中的每一列資料都是來自監控代理的Ping。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警報嚴重</b> </td> 
   <td colname="col2"> 從cs-uri-query(ad)值建立的數值Dimension。 它是在Ping層級建置，條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警報關閉</b> </td> 
   <td colname="col2"> 從cs-uri-query(ac)值建立的數值Dimension。 它是在Ping層級建置，條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>警報警告</b> </td> 
   <td colname="col2"> 從cs-uri-query(ae)值建立的數值Dimension。 它是在Ping層級建置，條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>任何設定檔重新處理</b> </td> 
   <td colname="col2"> 從cs-uri-query(aa)值建立的數值Dimension。 它是在Ping級別建置的，條件是cs-uri-query(a)與"1"匹配，而cs-uriquery(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>截止延遲分鐘數</b> </td> 
   <td colname="col2"> cs-uri-query(bi)會放入x-as-of-delay-minutes欄位中，並捨入至最接近的分鐘數。 它是在Ping層級建置，條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>能力行百分比</b> </td> 
   <td colname="col2"> 從cs-uri-query(r)值建立的數值Dimension。 它是在Ping級別建置的，條件是cs-uri-query(a)與"1"匹配，而cs-uriquery(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>容量大小百分比</b> </td> 
   <td colname="col2"> 從cs-uri-query(n)值建立的數值Dimension。 它是在Ping級別建置的，條件是cs-uri-query(a)與"1"匹配，而cs-uriquery(k)不是空的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>元件檢查成功</b> </td> 
   <td colname="col2"> 從cs-uri-query(v)值建立的簡單Dimension。 它是在Ping層級建置，且條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>出錯的元件</b> </td> 
   <td colname="col2"> cs-uri-query(ao)由"|"分隔字元分割，並複製到x-components-in-error欄位中。 從「錯誤中的x元件」欄位建立「多對多」Dimension。 在Ping層級建置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細檢查秒數</b> </td> 
   <td colname="col2"> 從cs-uri-query(l)值建立的數值Dimension。 它是在Ping級別建置的，條件是cs-uri-query(k)不為空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>詳細檢查成功</b> </td> 
   <td colname="col2"> 從cs-uri-query(k)值建立的簡單Dimension。 它是在Ping層級建置，條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>DimensionGigaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bc)被複製到x-dimension-gb欄位中。 x維GB欄位是此簡單Dimension的用戶，條件是cs-uri-query(a)匹配"2"。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>磁碟"x"已用百分比</b> </td> 
   <td colname="col2"> 這些數值Dimension是從cs-uri-query(ah, ai, aj, ak, al)值設定。 它們是在Ping級別構建的，且條件是cs-uri-query(a)匹配"1"，而cs-uri-query(k)不為空。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>估計掃描秒數</b> </td> 
   <td colname="col2"> 此「數值」Dimension中使用x-estimated-sweep-dekasseconds欄位。 這是伺服器的估計掃描時間除以10（減小掃描測量的解析度以使尺寸更合理）。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速輸入MegaBytes</b> </td> 
   <td colname="col2"> cs-uri-query(bj)值用於此維度。 區塊的最後一列會作為維度的值。 如果資料集為「快速輸入」，此數值Dimension的值將顯示系統輸入資料時的每分鐘MB。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>每分鐘快速合併MegaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bk)值用於此維度。 區塊的最後一列會作為維度的值。 如果資料集處於快速合併中此數值Dimension的值將顯示系統每分鐘合併的MB。 <p><p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>欄位GigaBytes</b> </td> 
   <td colname="col2">cs-uri-query(bg)值用於此維度。 此值除以1000，並四捨五入至最接近的整數。 此數值Dimension的值會顯示資料集中欄位所使用的空間量。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>群組</b> </td> 
   <td colname="col2"> 從cs-uri-query(x)值在Ping層級建立的簡單Dimension。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>主機</b> </td> 
   <td colname="col2"> cs-uri-query(b)值用於此維度。 簡單維的值是塊的最後一行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>上次Ping</b> </td> 
   <td colname="col2"> x-unixtime欄位會複製到x-last-ping中，並除以10以減少基數。 數值Dimension是在區塊層級建立，並使用x-last-ping欄位。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>載入平均</b> </td> 
   <td colname="col2"> 這是使用給定伺服器cs-uri-query(i)值的最後一行的數值維。 條件是cs-uri-query(k)不為空。 此維度用於計算所監視系統中伺服器的平均負載。 <p><p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>日誌讀取百分比</b> </td> 
   <td colname="col2">cs-uri-query(be)值用於此數值維，建置於Ping層級。 此維度用於計算讀取的記錄檔百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體頁檔案百分比</b> </td> 
   <td colname="col2"> 這是使用cs-uri-query(o)值的數值維，建置在Ping層級。 其條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合"1"。 此維度用於計算頁面檔案記憶體使用量的百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理兆位元組總數</b> </td> 
   <td colname="col2">這是使用cs-uri-query(ag)值的數值維，建置在Ping級別。 其條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合「1」。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體物理百分比</b> </td> 
   <td colname="col2">這是使用cs-uri-query(ag)值的數值維，建置在Ping級別。 其條件是cs-uri-query(k)不為空，而cs-uri-query(a)符合「1」。 此維度用於計算每個伺服器的物理記憶體使用率百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>記憶體查詢百分比</b> </td> 
   <td colname="col2"> 這是使用Ping級別cs-uri-query值的數值維。 其條件是cs-uri-query(k)不為空，cs-uri-query(a)符合「1」。 此維度用於計算每個伺服器的查詢記憶體使用率百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>網路連接</b> </td> 
   <td colname="col2"> 這是使用在Ping層級建置的cs-uri-query(q)值的數值維度。 其條件是cs-uri-query(k)不為空，cs-uri-query(a)符合「1」。 這用於顯示指定伺服器的網路連接數。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輸出行</b> </td> 
   <td colname="col2"> cs-uri-query(bh)值被100000除，並複製到x-output-rows欄位中以減小維的大小。 X-output-rows用於在Ping級別構建的數值Dimension，條件是cs-uri-query(a)與"2"匹配。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Ping類型ID</b> </td> 
   <td colname="col2"> 在Ping級別使用cs-uri-query(a)值構建的簡單Dimension。 這顯示錄制了哪種Ping。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>輪詢延遲（秒）</b> </td> 
   <td colname="col2">cs-uri-query(m)值除以10以縮小維度大小，並複製到x-poll-latency-centiseconds欄位中。 這是在Ping層級建置的數值維度，條件是cs-uri-query(k)不空白，且cs-uri-query(a)符合"1"/此維度用於計算輪詢延遲。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>處理模式ID</b> </td> 
   <td colname="col2"> cs-uri-query(bb)值用於此SimpleDimension，建置在Ping級別。 條件是cs-uri-query(bb)不為空，而cs-uri-query(a)與「2」處理模式ID匹配，這樣就可以查看系統處於何種處理模式（快速輸入、快速合併、即時）。 <p>注意：此維度會隱藏，然後在用戶端維度處理模式中以好記的值重新公開。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>設定檔</b> </td> 
   <td colname="col2"> cs-uri-query(ba)值用於此簡單Dimension，它是在Ping級別構建的。 此維度會顯示目前監控之設定檔的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查秒數</b> </td> 
   <td colname="col2"> cs-uri-query(h)值用於此數值Dimension。 它是在Ping層級建置，條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>快速檢查成功</b> </td> 
   <td colname="col2"> 這是從cs-uri-query(g)值建立的簡單維，該值是在Ping級別建立的。 用於計算快速檢查量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>即時處理百分比</b> </td> 
   <td colname="col2"> 數值Dimension，使用在Ping層級建置的cs-uri-query(t)值。 條件是cs-uri-query(a)符合「1」。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>源最後</b> </td> 
   <td colname="col2"> 從在Ping級別建立的cs-uri-query(bl)值建立的簡單Dimension。 此維度會顯示上次與資料來源聯絡的時間。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>臨時DB空間百分比</b> </td> 
   <td colname="col2">使用cs-uri-query(an)值建置的數值Dimension，在Ping層級建置。 條件是cs-uri-query(k)不為空，且cs-uri-query(a)符合「1」。 它用於計算指定伺服器上已用臨時資料庫空間的百分比。 <p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>轉換百分比</b> </td> 
   <td colname="col2">cs-uri-query(bf)值用於此數值維度。 是在Ping層級建置。 此維度用於計算完成資料轉換的百分比。 <p><p>注意：此維度會隱藏，因為它只有在平均到量度時才有用。 </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版本</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值用於此簡單Dimension。 它是在Ping層級建置，且條件是cs-uri-query(ab)不是空的，且cs-uri-query(a)符合「1」。 這會顯示每個伺服器上執行的Data Workbench伺服器版本。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Workbench版本主要</b> </td> 
   <td colname="col2"> cs-uri-query(ab)值會被分割，而主要發行值會複製到x-insight-version-major欄位中。 這是在Ping層級建置的SimpleDimension，條件是x-insight-version-major不是空的，且cs-uri-query(a)符合「1」。 </td> 
  </tr> 
 </tbody> 
</table>

<!-- <a id="section_76D8A4B07BB947558EBED1123EA203D5"></a> -->
