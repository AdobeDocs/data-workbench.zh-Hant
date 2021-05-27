---
description: Data Workbench伺服器(InsightServer64.exe)可從具有符合ODBC 3.0驅動程式的任何SQL資料庫(例如，Oracle或Microsoft SQL Server)讀取事件資料。
title: ODBC 資料來源
uuid: 5b37cd41-2d79-472c-8e6d-00ff894991a9
exl-id: b22b1e27-9b6c-4708-b45c-a9605807689a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1245'
ht-degree: 1%

---

# ODBC 資料來源{#odbc-data-sources}

Data Workbench伺服器(InsightServer64.exe)可從具有符合ODBC 3.0驅動程式的任何SQL資料庫(例如，Oracle或Microsoft SQL Server)讀取事件資料。

Data Workbench伺服器的ODBC支援與從Sensor或外部程式產生的記錄檔載入資料的現有支援類似。 但是，還有一些額外的考量和限制：

* Data Workbench伺服器的ODBC支援與叢集功能相容。 資料分佈於所有處理伺服器之間，所有後續處理（包括查詢處理）都能充分受益於群集。
* ODBC支援取決於第三方ODBC驅動程式。 要使ODBC支援發揮作用，必須使用Adobe平台外部的工具，在Data Workbench伺服器運行的電腦上配置這些驅動程式。 Data Workbench電腦不需要任何額外設定。
* 從中載入資料的表或視圖必須具有遞增的ID列。 對於任何行，此列中的值（可能是表中的實際列或任何SQL清單達式）不能隨著新行插入到資料庫而降低。 如果違反此限制，資料就會遺失。 為獲得足夠的效能，此列或清單達式需要索引。

   >[!NOTE]
   >
   >多行在[!DNL Increasing ID]列中可以有相同的值。 一種可能是時間戳列，其精度不及理想。

* Data Workbench伺服器無法載入資料長度較長的欄（使用中特定資料庫應用程式所判斷，超過特定長度的資料）。
* 從資料庫中檢索資料的速度比從磁碟檔案中讀取資料的速度慢。 從ODBC源載入資料的資料集處理時間（尤其是重新處理時）比資料來自Sensor或其他磁碟檔案的等同大小資料集長得多。

如需重新處理資料的詳細資訊，請參閱[重新處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

**為ODBC配置Insight Server[!DNL event data]**

若要將Data Workbench伺服器設定為從SQL資料庫載入資料，您必須先依序執行下列步驟：

1. 在處理資料集的資料工作台伺服器電腦上安裝適當的資料庫客戶端軟體，包括ODBC驅動程式。

   >[!NOTE]
   >
   >如果要載入ODBC事件資料以在Data Workbench伺服器叢集上處理，則必須在叢集中的所有處理伺服器上安裝資料庫用戶端軟體。 有關在群集中指定處理伺服器的資訊，請參閱&#x200B;*伺服器產品安裝和管理指南*。

1. 使用Windows的ODBC資料源管理員配置資料源。

   請務必注意，Data Workbench伺服器(InsightServer64.exe)會以Windows服務的形式執行。 因此，資料源通常必須配置為系統DSN，而不是用戶DSN，資料工作台伺服器才能使用它。 您可以在資料庫軟體的文檔中找到有關此配置步驟的詳細資訊。

在適當的Data Workbench伺服器電腦上安裝資料庫客戶端軟體後，您可以針對所需配置檔案編輯[!DNL Log Processing]配置檔案中的適當參數，將資料集配置為使用ODBC資料源。

## 參數 {#section-15c0218d93364693a565f2609a12f73e}

對於使用開放資料庫連接(ODBC)標準的資料庫中的資料，可使用以下參數：

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
   <td colname="col2"> DSN（由處理資料集的Data Workbench伺服器電腦的管理員提供），指要從中載入資料的資料庫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫密碼 </td> 
   <td colname="col2"> 連接到資料庫時要使用的口令。 如果為<span class="wintitle">資料源管理員</span>中的DSN配置了密碼，則這可能留空。 此處提供的任何密碼將覆蓋<span class="wintitle">資料源管理員</span>中為DSN配置的密碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫用戶ID </td> 
   <td colname="col2"> 連接到資料庫時要使用的用戶ID。 如果已為<span class="wintitle">資料源管理員</span>中的DSN配置了用戶ID，則此ID可能留空。 此處提供的任何用戶ID將覆蓋為<span class="wintitle">資料源管理員</span>中的DSN配置的用戶ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 欄位 </td> 
   <td colname="col2"> 欄物件的向量，指定從資料庫中的資料欄對應至Data Workbench伺服器執行引擎中的資料欄位。 每個列都包含<span class="wintitle">列名</span>和<span class="wintitle">欄位名</span>。 <span class="wintitle"> 列</span> 名稱是SQL清單達式，在上面所述的表標識符所標識的表的上下文中 <span class="wintitle"> 必</span> 須有效。它可以是列名或任何基於表中任意列數的SQL表達式。 若要以不會失去精確度的方式，將特定資料類型的值轉換為字串，可能需要格式化函式。 所有資料都使用資料庫的預設格式化方法隱式轉換為字串，如果不使用顯式格式化表達式，這可能會導致某些列資料類型（如日期/時間資料類型）的資料丟失。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 增加ID欄 </td> 
   <td colname="col2"> <p>列名或SQL清單達式，它滿足添加新行時其增加（或至少不減少）的標準。 也就是說，如果在行A之後將行B添加到表中，則行B中此列（或清單達式）的值必須大於（根據資料庫的本機排序順序），而不是行A中的相應值。 </p> <p> 
     <ul id="ul_EBF6AEE4746B41B3B5BB6CC74194DAED"> 
      <li id="li_A5C9BE52B01649DE9726ECEC68B99828"> <span class="wintitle">增加ID列</span>名稱可能與現有列的名稱相同，但不需要。 </li> 
      <li id="li_CF69EAB4AFB14F4894F7A5CDCAF06947"> 假定此表達式具有SQL字元資料類型。 如果實際增加的ID欄屬於其他資料類型，此值必須是欄運算式，才能將其轉換為字串。 因為這通常表示比較是字典（逐字元），因此請務必謹慎設定值格式。 </li> 
      <li id="li_58977431962E48039C898CFC47C53323"> 表達式用於SQL ORDER BY子句，並與SQL WHERE子句中的表達式進行比較。 在使用的確切清單達式上建立索引至關重要。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌源ID </td> 
   <td colname="col2"> <p>此參數的值可以是任何字串。 如果指定了值，此參數可讓您區分不同日誌源中的日誌條目，以用於源標識或目標處理。 x-log-source-id欄位中會填入一個值，用於識別每個記錄項目的記錄來源。 例如，如果要標識名為ODBCSource01的ODBC源中的日誌條目，則可以從ODBCSource01鍵入<span class="filepath">。</span> 而該字串將傳遞至該來源每個記錄項目的x-log-source-id欄位。 </p> <p> 有關x-log-source-id欄位的資訊，請參閱<a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f">事件資料記錄欄位</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 在伺服器上運行 </td> 
   <td colname="col2"> 處理伺服器的<span class="filepath"> profile.cfg</span>檔案中的索引值，該處理伺服器進行ODBC查詢以從資料庫獲取資料。 （<span class="filepath"> profile.cfg</span>檔案中的Processing Server參數會列出資料集的所有處理伺服器，且每個伺服器都有索引值，第一個為0。） 預設值為 0。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 表格識別碼 </td> 
   <td colname="col2"> 一種SQL表達式，它為要從中載入資料的表或視圖命名。 典型表標識符的格式為SCHEMA.TABLE。 </td> 
  </tr> 
 </tbody> 
</table>

此範例顯示Data Workbench中具有ODBC資料來源的[!DNL Log Processing]設定視窗。 此資料源從名為[!DNL VISUAL.VSL]的資料庫中的[!DNL Data Source Name] &quot;VSTestO&quot;的表中獲取資料。 五(5)個欄物件([!DNL Fields])將資料從資料庫中的資料欄對應至Data Workbench伺服器。

![](assets/cfg_LogProcessing_LogSources_ODBC.png)
