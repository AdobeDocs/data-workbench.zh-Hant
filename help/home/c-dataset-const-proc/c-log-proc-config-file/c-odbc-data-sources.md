---
description: 資料工作台伺服器(InsightServer64.exe)可以從任何具有ODBC 3.0相容驅動程式的SQL資料庫（例如Oracle或Microsoft SQL Server）讀取事件資料。
solution: Analytics
title: ODBC資料源
topic: Data workbench
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# ODBC資料源{#odbc-data-sources}

資料工作台伺服器(InsightServer64.exe)可以從任何具有ODBC 3.0相容驅動程式的SQL資料庫（例如Oracle或Microsoft SQL Server）讀取事件資料。

資料工作台伺服器的ODBC支援類似於現有對從感測器或外部進程生成的日誌檔案載入資料的支援。 但是，還有一些額外的考量和限制：

* 資料工作台伺服器的ODBC支援與群集功能相容。 資料會分佈在所有處理伺服器之間，而所有後續處理（包括查詢處理）都可充分受益於叢集。
* ODBC支援取決於第三方ODBC驅動程式。 要使用ODBC支援，必須使用Adobe平台外部的工具在資料工作台伺服器運行的電腦上配置這些驅動程式。 資料工作台電腦不需要任何額外的設定。
* 從中載入資料的表或視圖必須具有增加的ID列。 對於任何行，此列中的值（可能是表中的實際列或任何SQL清單達式）不能隨著新行插入到資料庫中而減小。 如果違反此限制，資料就會遺失。 為獲得足夠的效能，此列或清單達式需要索引。

   >[!NOTE]
   >
   >多行在列中可能具有相同的 [!DNL Increasing ID] 值。 一種可能是時間戳列，其精度不夠理想。

* 資料工作台伺服器無法載入長資料欄（使用中特定資料庫應用程式所決定的超過特定長度的資料）。
* 從資料庫中檢索資料比從磁碟檔案中讀取資料慢。 從ODBC源載入資料的資料集的處理時間（尤其是在重新處理時）比從感測器或其他磁碟檔案載入資料的同等大小的資料集要長得多。

如需重新處理資料的詳細資訊，請參 [閱重新處理和轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

**為ODBC配置Insight Server[!DNL event data]**

要配置資料工作台伺服器以從SQL資料庫載入資料，必須首先按順序執行以下步驟：

1. 在處理資料集的資料工作台伺服器上安裝適當的資料庫客戶端軟體，包括ODBC驅動程式。

   >[!NOTE]
   >
   >如果要在資料工作台伺服器群集上載入ODBC事件資料以進行處理，則必須在群集中的所有處理伺服器上安裝資料庫客戶端軟體。 有關在群集中指定處理伺服器的資訊，請參 *閱伺服器產品安裝和管理指南*。

1. 使用Windows的ODBC資料源管理器配置資料源。

   請務必注意，資料工作台伺服器(InsightServer64.exe)會以Windows服務的形式執行。 因此，資料源通常必須配置為系統DSN，而不是用戶DSN才能使用資料工作台伺服器。 有關此配置步驟的詳細資訊，請參閱資料庫軟體的文檔。

將資料庫客戶端軟體安裝到相應的資料工作台伺服器電腦上後，可以通過編輯所需配置檔案的配置檔案中的相應參數，將資料集配置為 [!DNL Log Processing] 使用ODBC資料源。

## 參數 {#section-15c0218d93364693a565f2609a12f73e}

對於使用Open Database Connectivity(ODBC)標準的資料庫資料，可使用以下參數：

<table id="table_606D8A90DA4A43C29F2C6130F8C753F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> ODBC源的標識符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料來源名稱 </td> 
   <td colname="col2"> DSN由資料工作台伺服器機器的管理員提供，其中資料集被處理在該伺服器機器上，該DSN是指要從其載入資料的資料庫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫口令 </td> 
   <td colname="col2"> 連接資料庫時要使用的口令。 如果已在「 <span class="wintitle"> Data Source Administrator（資料源管理員）」中為DSN配置了密碼</span>，則此密碼可能保留為空。 此處提供的任何口令將覆蓋「資料源管理員」中為DSN配置 <span class="wintitle"> 的口令</span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫用戶ID </td> 
   <td colname="col2"> 連接資料庫時要使用的用戶ID。 如果已在「 <span class="wintitle"> Data Source Administrator（資料源管理員）」中為DSN配置了用戶ID</span>，則此ID可能保留為空。 此處提供的任何用戶ID將覆蓋「資料源管理員」中為DSN配置的 <span class="wintitle"> 用戶ID</span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 欄位 </td> 
   <td colname="col2"> 列對象的向量，它指定從資料庫中的資料列到資料工作台伺服器執行引擎中的資料欄位的映射。 每列都有「列 <span class="wintitle"> 名</span> 」和「 <span class="wintitle"> 欄位名」條目</span>。 <span class="wintitle"> Column Name</span> （列名）是SQL清單達式，在上述表標識符所標識的表的上下文中 <span class="wintitle"> 必須有效</span> 。 它可以是基於表中任意數目的列名或任何SQL表達式。 格式化函式可能是必要的，以不損失精確度的方式將某些資料類型的值轉換為字串。 所有資料都會使用資料庫的預設格式化方法隱式轉換為字串，若未使用明確格式化運算式，可能會造成某些欄資料類型（例如日期／時間資料類型）的資料遺失。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 增加ID欄 </td> 
   <td colname="col2"> <p>列名或SQL清單達式，它滿足在添加新行時增加（或至少不減少）的標準。 也就是說，如果在行A之後將行B添加到表中，則行B中的此列（或清單達式）的值必須大於行A中的相應值（根據資料庫的本地排序順序）。 </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> 「增 <span class="wintitle"> 加ID欄 </span>名稱」可能與現有欄的名稱相同，但不需要。 </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> 假定此表達式具有SQL字元資料類型。 如果實際增加的ID欄屬於某些其他資料類型，此值必須是欄運算式，才能將其轉換為字串。 因為這通常意味著比較是辭彙排版（逐個字元），所以務必謹慎格式化值。 </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> 該表達式用於SQL ORDER BY子句中，並與SQL WHERE子句中進行比較。 請務必在使用的精確欄運算式上建立索引。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌源ID </td> 
   <td colname="col2"> <p>此參數的值可以是任何字串。 如果指定了值，此參數可讓您區分不同日誌源中的日誌條目，以用於源標識或目標處理。 x-log-source-id欄位會填入一個值，用以識別每個記錄項目的記錄來源。 例如，如果要從名為ODBCSource01的ODBC源中標識日誌項，則可以從ODBCSource01 <span class="filepath"> 中鍵入。</span> 而該字串則會傳遞至x-log-source-id欄位，以供來自該來源的每個記錄項目使用。 </p> <p> 如需x-log-source-id欄位的詳細資訊，請參閱事件資 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> 料記錄欄位</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 在伺服器上執行 </td> 
   <td colname="col2"> 處理伺服器 <span class="filepath"> 的profile.cfg</span> 檔案中的索引值，該檔案使ODBC查詢從資料庫獲取資料。 (profile.cfg檔案中的「處理伺服器」參 <span class="filepath"></span> 數會列出資料集的所有處理伺服器，而每個伺服器都有索引值，第一個為0。)預設值為 0。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 表格識別碼 </td> 
   <td colname="col2"> 一個SQL表達式，它命名要從中載入資料的表或視圖。 典型表標識符的格式為SCHEMA.TABLE。 </td> 
  </tr> 
 </tbody> 
</table>

此示例顯示了 [!DNL Log Processing] 資料工作台中具有ODBC資料源的配置窗口。 此資料源從名為&quot;VSTestO&quot;的數 [!DNL VISUAL.VSL] 據庫中的表 [!DNL Data Source Name] 中獲取資料。 五(5)欄物件( [!DNL Fields])將資料庫中資料欄的資料對應至資料工作台伺服器。

![](assets/cfg_LogProcessing_LogSources_ODBC.png)

