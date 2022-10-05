---
description: 您可用來將查詢資料併入資料集之轉換的相關資訊。
title: 定義查閱轉換
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
exl-id: 7b1504be-8669-4340-8400-e33f9663b602
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2288'
ht-degree: 2%

---

# 定義查閱轉換{#defining-lookup-transformations}

{{eol}}

您可用來將查詢資料併入資料集之轉換的相關資訊。

請注意，並非所有類型都可在資料集建構程式的兩個階段期間使用。

* [分類](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## 分類 {#section-8474376c14e54d14ae73749696ada468}

此 [!DNL Categorize] 轉換使用由模式字串/值組組成的兩欄查閱表格。 在此轉換期間，Data Workbench伺服器會依序讀取每個事件資料記錄，並將記錄中指定欄位的內容與查閱表格第一欄所列的每個模式字串進行比較。 如果指定欄位符合其中一個模式字串，Data Workbench伺服器會將與該模式字串相關聯的值（在第二欄中找到）寫入記錄中的指定輸出欄位。

查詢表格第一欄中的字串（可選）可以以^字元開頭和/或以$字元結尾，以強制在開頭和/或結尾匹配。 此轉換不接受在第一欄中定義匹配條件的規則運算式。 如果輸入值是字串的向量，則每個字串通過轉換運行，並將結果附加到輸出字串向量。

A [!DNL Categorize] 轉換通常比使用 [!DNL Regular Expression] 轉型以完成相同的任務。

>[!NOTE]
>
>中使用的子字串測試 [!DNL Categorize] 區分大小寫，除非使用 [!DNL Case Sensitive] 參數。

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 區分大小寫 </td> 
   <td colname="col2"> True或False。 指定子字串測試是否區分大小寫。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 套用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設 </td> 
   <td colname="col2"> 如果條件測試通過且分類檔案中沒有任何條目與輸入匹配，或者給定日誌條目中未定義輸入欄位時，要使用的預設值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用來分隔查詢檔案中欄的字串。 長度必須為單一字元。 </p> <p> 按住Ctrl鍵並在「分隔字元」參數內按一下滑鼠右鍵， <span class="wintitle"> 插入</span> 中。 此菜單包含通常用作分隔符的特殊字元的清單。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多個值 </td> 
   <td colname="col2"> True或False。 若為true，當檔案中的多列符合輸入時，每個符合都會導致值附加至字串的輸出向量。 若為false，則輸出中只會使用檔案中的第一個相符列。 在後一種情況下，如果輸入是向量，則輸出也是等效長度的向量。 如果輸入是簡單字串，則輸出也是簡單字串。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檔案 </td> 
   <td colname="col2"> 分類檔案的路徑和檔案名。 相對路徑與Data Workbench伺服器的安裝目錄有關。 此檔案通常位於Data Workbench伺服器安裝目錄的「查閱」目錄中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 分類檔案會比對其子字串與此欄位中的值，以識別檔案中的相符列。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 與結果關聯的欄位名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**分類的考量事項**

* 中查閱檔案的變更 [!DNL Categorize] 定義於 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案需要重新轉換資料集。 的查閱檔案 [!DNL Categorize] 定義於 [!DNL Log Processing.cfg] 檔案或 [!DNL Log Processing Dataset Include] 檔案不受此限制。 如需重新處理資料的詳細資訊，請參閱 [重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL Categorize] 定義於 [!DNL Log Processing.cfg] 檔案或 [!DNL Log Processing Dataset Include] 檔案會在查詢檔案變更時重新載入其查詢檔案。 變更不會回溯套用，但會套用至變更發生後讀取的所有記錄資料。

此範例說明如何使用 [!DNL Categorize] 轉換，將查詢資料與從網站流量收集的事件資料整合。 假設特定網站有業務區域，且需要能夠根據不同區域產生的流量和值來查看和比較。 您可以建立查詢檔案，列出用來識別這些不同區段的子字串。

查閱檔案 [!DNL Lookups\custommap.txt] 包含下表：

| /products/ | 產品 |
|---|---|
| ^/sports/ | 運動 |
| ^/新聞/ | 新聞 |
| ... | ... |

此分類檔案會將包含字串「/products/」的任何項目對應至「Products」值，將任何以「/sports/」開頭的項目對應至「Sports」值，並將任何以「/news/」開頭的項目對應至「News」值。 以下分類轉換使用cs-uri-stem欄位中的值作為我們在其中查找匹配子字串的字串。 轉換的結果會放入x-custommap欄位中。

![](assets/cfg_TransformationType_Categorize.png)

假設Multiple Values參數設為false，則該示例將為x-custommap生成以下值，給定cs-uri-stem的所列值。

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | 運動 |
| [!DNL /sports/products/buy.php] | 產品 |
| [!DNL /news/headlines.php] | 新聞 |
| [!DNL /news/products/subscribe.php] | 產品 |

輸出是根據查閱檔案中子字串的順序。 例如， cs-uri-stem [!DNL /sports/products/buy.php] 傳回&quot;Products&quot;。 雖然URI主體以「/sports/」開頭，但在查閱檔案中，字串「/products/」會列在「/sports/」之前。 如果Multiple Values參數設為true,x-custommap會有額外的值，因為上一個範例會符合查詢表格中的兩列：產品與新聞。

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

此 [!DNL FlatFileLookup] 轉換使用由任意數量的列和行組成的查找表（儘管可以回憶它駐留在記憶體中）。 在這種轉換類型期間，Data Workbench伺服器會依序讀取每個事件資料記錄，並將記錄中指定欄位的內容與查閱表格之指定欄中的每個值比較。 如果有相符項目，Data Workbench伺服器會將一或多個值從查閱表格中的相符列寫入事件資料記錄中的一或多個指定輸出欄位。

此轉換期間使用的查閱表格會從您定義轉換時指定位置的平面檔案中填入。

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 套用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設 </td> 
   <td colname="col2"> 若符合條件，且查閱檔案中沒有任何項目符合輸入，則使用的預設值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用來分隔查詢檔案中欄的字串。 長度必須為單一字元。 </p> <p> 按住Ctrl鍵並在「分隔字元」參數內按一下滑鼠右鍵， <span class="wintitle"> 插入</span> 中。 此菜單包含通常用作分隔符的特殊字元的清單。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檔案 </td> 
   <td colname="col2"> 查閱檔案的路徑和檔案名。 相對路徑與Data Workbench伺服器的安裝目錄有關。 此檔案通常位於Data Workbench Server安裝目錄的「查閱」目錄中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 標題列 </td> 
   <td colname="col2"> True或False。 指出表格中的第一列是要在處理時忽略的標題列。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <span class="wintitle"> 欄名稱</span> 是欄的名稱，用於將輸入與檔案中的列匹配。 如果標題列為true，則可以是查閱檔案中欄的名稱。 否則，這必須是要比對的零基列號。 <span class="wintitle"> 欄位名稱</span> 是用於在查閱檔案中找出列的欄位名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多個值 </td> 
   <td colname="col2"> <p>True或False。 決定是否應傳回單一值（相符列）或多個值（每個相符列各一個）。 </p> <p> <p>注意：若 <span class="wintitle"> 多個值</span> 設為false，則您必須確定沒有多個相符項目。 發生多個相符項目時，無法保證會傳回哪個相符項目。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> <p>列對象（結果）的向量，每個對象由列和欄位名稱定義。 </p> <p> <span class="wintitle"> 欄名稱</span> 是從中獲取輸出值的列。 若 <span class="wintitle"> 標題列</span> 為true，則可以是查詢檔案中欄的名稱。 否則，這必須是要比對的零基列號。 </p> <p> <span class="wintitle"> 欄位名稱</span> 是用於擷取輸出的欄位名稱。 請注意，這可以是結果的向量，若Multiple Values參數為true，則每行識別一個。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**的考量事項[!DNL FlatFileLookup]**

* 將輸入欄位與查閱檔案配對一律區分大小寫。
* 中查閱檔案的變更 [!DNL FlatFileLookup] 定義於 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案需要重新轉換資料集。 的查閱檔案 [!DNL FlatFileLookup] 定義於 [!DNL Log Processing.cfg] 檔案或 [!DNL Log Processing Dataset Include] 檔案不受此限制。 如需重新處理資料的詳細資訊，請參閱 [重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

* [!DNL FlatFileLookup] 轉換 [!DNL Log Processing.cfg] 檔案或 [!DNL Log Processing Dataset Include] 檔案會在查詢檔案變更時重新載入其查詢檔案。 變更不會回溯套用，但會套用至變更發生後讀取的所有記錄資料。

此範例說明如何使用 [!DNL FlatFileLookup] 轉換，將查詢資料與從網站流量收集的事件資料整合。 假設您想要隔離將流量路由至網站的網站合作夥伴，並將其合作夥伴ID轉換為更方便使用的名稱。 然後，您可以使用好記的名稱來建立延伸維度和視覺效果，這些維度和視覺效果比用於路由流量的站點對站點關係更能清楚地對應至業務關係。

範例轉換會搜尋cs(referrer-query)欄位以取得PartnerID名稱值組，若找到則會搜尋查閱檔案 [!DNL Lookups\partners.txt] 用於比較PartnerID值與 [!DNL Partner] 欄。 如果找到列，輸出欄位x-partner-name會從 [!DNL PrintName] 欄。

![](assets/cfg_TransformationType_FlatFileLookup.png)

如果查閱表格包含下列資訊：

| ID | 合作夥伴 | 已開始 | PrintName |
|---|---|---|---|
| 1 | P154 | 1999年8月21日 | Yahoo |
| 2 | P232 | 2000年7月10日 | Microsoft |
| 3 | P945 | 2001年1月12日 | Amazon |

下列範例將轉換如下：

* 如果cs(referrer)(PartnerID)傳回P232，則欄位x-partner-name的值將會是「Microsoft」。
* 如果cs(referrer)(PartnerID)傳回P100，則欄位x-partner-name的值將會是「無合作夥伴」。
* 如果cs(referrer)(PartnerID)未傳回任何內容，則欄位x-partner-name的值將會指定為「無合作夥伴」，如預設參數所指定。

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

此 [!DNL ODBCLookup] 轉換的運作方式如同 [!DNL FlatFileLookup] 轉換。 唯一的區別是，此轉換期間使用的查閱表從ODBC資料庫中填入，而不是平面檔案。

>[!NOTE]
>
>[!DNL ODBCLookup] 轉換只能在資料集建構程式的轉換階段執行。 如果可能，Adobe建議您使用 [!DNL FlatFileLookup] 轉換，而非 [!DNL ODBCLookup] 轉換。 [!DNL FlatFileLookup] 轉換在本質上更可靠，因為它們不依賴於外部系統的可用性。 此外，如果查找表位於您控制本地的平面檔案中，則修改該查詢表的風險也較小。

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 套用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料來源名稱 </td> 
   <td colname="col2"> DSN（由處理資料集的Data Workbench伺服器電腦的管理員提供），指要從中載入資料的資料庫。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫密碼 </td> 
   <td colname="col2">連接到資料庫時要使用的口令。 如果為 <span class="wintitle"> 資料來源管理員</span>，則可保留空白。 此處提供的任何密碼將覆蓋為 <span class="wintitle"> 資料來源管理員</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫用戶ID </td> 
   <td colname="col2">連接到資料庫時要使用的用戶ID。 如果已為 <span class="wintitle"> 資料來源管理員</span>，則可保留空白。 此處提供的任何用戶ID將覆蓋為中的DSN配置的用戶ID <span class="wintitle"> 資料來源管理員</span>. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設 </td> 
   <td colname="col2"> 若符合條件，且查閱檔案中沒有任何項目符合輸入，則使用的預設值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入欄 </td> 
   <td colname="col2"> <span class="wintitle"> 欄名稱</span> 是與輸入匹配的資料的列名或SQL表達式。 <span class="wintitle"> 欄位名稱</span> 是包含要查閱之資料的欄位名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多個值 </td> 
   <td colname="col2"> <p>True或False。 決定是否應傳回單一值（相符列）或多個值（每個相符列各一個）。 </p> <p> <p>注意：若 <span class="wintitle"> 多個值</span> 設為false，則您必須確定沒有多個相符項目。 發生多個相符項目時，無法保證會傳回哪個相符項目。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出列 </td> 
   <td colname="col2"> <p>列對象（結果）的向量，其中每個對象由列和欄位名稱定義。 </p> <p> <span class="wintitle"> 欄名稱</span> 是從中獲取輸出值的列的或SQL表達式的名稱。 <span class="wintitle"> 欄位名稱</span> 是用於擷取輸出的欄位名稱。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 表格識別碼</span> </td> 
   <td colname="col2"> 一種SQL表達式，它為要從中載入資料的表或視圖命名。 典型表標識符的格式為SCHEMA.TABLE。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* 資料來源名稱， [!DNL Database User ID], [!DNL Database Password]、和表標識符參數與ODBC資料源描述的相同名稱的參數相同。 請參閱 [ODBC資料源](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* 與ODBC資料源不同， [!DNL ODBCLookup] 轉換不需要增加的ID欄。 請參閱 [ODBC資料源](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). 這是因為當資料集作用中時，查閱表格的內容不得變更。 在重新轉換發生之前，無法偵測查閱表格或檢視中的變更。 如需重新處理資料的詳細資訊，請參閱 [重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

假設您要將過期的DNS記錄轉換為更新的記錄。 這兩組記錄都儲存在SQL資料庫中。 要執行此任務，您將引用從資料庫生成的查找表並替換過期的DNS記錄。

我們的範例轉換會搜尋s-dns欄位的記錄項目，如果找到，則會使用查閱表格VISUAL.LOOKUP來比較s-dns項目與 [!DNL OLDDNS] 欄。 如果表格中有列，輸出欄位s-dns會從 [!DNL NEWDNS] 欄。

![](assets/cfg_TransformationType_ODBCLookup.png)
