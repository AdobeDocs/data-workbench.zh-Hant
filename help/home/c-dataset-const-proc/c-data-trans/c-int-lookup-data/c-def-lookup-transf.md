---
description: 您可用來將查閱資料併入資料集之轉換的相關資訊。
solution: Analytics
title: 定義查閱轉換
topic: Data workbench
uuid: 4f7358b1-9e6a-4d03-b0c6-411e454fc11e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 定義查閱轉換{#defining-lookup-transformations}

您可用來將查閱資料併入資料集之轉換的相關資訊。

請注意，並非所有類型都可在資料集建構程式的兩個階段中使用。

* [分類](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-8474376c14e54d14ae73749696ada468)
* [FlatFileLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-e09b2eeb96444a859b14f03cdaab31f2)
* [ODBCLookup](../../../../home/c-dataset-const-proc/c-data-trans/c-int-lookup-data/c-def-lookup-transf.md#section-4dcc3747e42e45c0a057e85f308a83cc)

## 分類 {#section-8474376c14e54d14ae73749696ada468}

轉 [!DNL Categorize] 換使用由模式字串／值對組成的雙列查閱表。 在此轉換期間，資料工作台伺服器依次讀取每個事件資料記錄，並將記錄中指定欄位的內容與查找表第一列中列出的每個模式字串進行比較。 如果指定欄位與其中一個模式字串匹配，則資料工作台伺服器將與該模式字串相關聯的值（在第二列中找到）寫入記錄中的指定輸出欄位。

查閱表格第一欄中的字串（可選）可以以$字元中的^字元和／或結尾開頭，以強制在開頭和／或結尾進行比對。 此轉換不接受在第一欄中定義匹配條件的規則運算式。 如果輸入值是字串的向量，則每個字串都通過轉換運行，並將結果附加到輸出字串向量。

轉換 [!DNL Categorize] 通常比使用轉換來完成相同的工作 [!DNL Regular Expression] 更簡單、更快速。

>[!NOTE]
>
>除非使用參數另有指 [!DNL Categorize] 定，否則所用的子字串測試會區分大小寫 [!DNL Case Sensitive] 。

<table id="table_1773344FAAE34BD4919CC4414249FDEE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
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
   <td colname="col2"> 是非。 指定子字串測試是否區分大小寫。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設值 </td> 
   <td colname="col2"> 如果條件測試通過且分類檔案中沒有條目與輸入匹配，或給定日誌條目中未定義輸入欄位，則使用的預設值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用來分隔查閱檔案中欄的字串。 長度必須為單一字元。 </p> <p> 如果按住Ctrl鍵並在分隔字元參數內按一下滑鼠右鍵，則會出現「插入 <span class="wintitle"> 」功能表</span> 。 此功能表包含常用作分隔字元的特殊字元清單。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多重值 </td> 
   <td colname="col2"> 是非。 如果為true，則當檔案中的多列符合輸入時，每一列符合都會產生值附加至字串的輸出向量。 如果為false，則輸出中只使用檔案中第一個匹配行。 在後一種情況下，如果輸入是向量，則輸出也是等效長度的向量。 如果輸入是簡單字串，則輸出也是簡單字串。 </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檔案 </td> 
   <td colname="col2"> 分類檔案的路徑和檔案名。 相對路徑與資料工作台伺服器的安裝目錄有關。 此檔案通常位於資料工作台伺服器安裝目錄內的「查閱」目錄中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 分類檔案將其子字串與此欄位中的值匹配，以標識檔案中的匹配行。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 與結果關聯的欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**分類注意事項**

* 在檔案或檔案中定 [!DNL Categorize] 義的轉換中查 [!DNL Transformation.cfg] 閱檔案的變更需 [!DNL Transformation Dataset Include] 要重新轉換資料集。 在檔案或檔 [!DNL Categorize] 案中定義之轉 [!DNL Log Processing.cfg] 換的查閱 [!DNL Log Processing Dataset Include] 檔案不受此限制。 如需重新處理資料的詳細資訊，請參 [閱重新處理和轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL Categorize] 在檔案或檔案中定 [!DNL Log Processing.cfg] 義的轉換會在查 [!DNL Log Processing Dataset Include] 閱檔案更改時重新載入其查找檔案。 更改不會追溯應用，但會應用於更改發生後讀取的所有日誌資料。

此範例說明如何使用轉換 [!DNL Categorize] 來整合查閱資料與從網站流量收集的事件資料。 假設特定網站有業務區域，而且需要能夠根據不同區域產生的流量和值來檢視和比較。 您可以建立查閱檔案，其中列出用以識別這些不同區段的子字串。

查閱檔案 [!DNL Lookups\custommap.txt] 包含下表：

| /products/ | 產品 |
|---|---|
| ^/sports/ | 運動 |
| ^/新聞/ | 新聞 |
| ... | ... |

此分類檔案將包含字串&quot;/products/&quot;的任何內容映射到&quot;Products&quot;值，任何以&quot;/sports/&quot;開頭的內容映射到&quot;Sports&quot;值，任何以&quot;/news/&quot;開頭的內容都映射到&quot;News&quot;值。 以下分類轉換使用cs-uri-stem欄位中的值作為我們尋找相符子字串的字串。 轉換的結果將放入x-custommap欄位。

![](assets/cfg_TransformationType_Categorize.png)

假設Multiple Values參數設為false，則此範例會針對cs-uri-stem列出的值，產生x-custommap的下列值。

| [!DNL cs-uri-stem] | [!DNL x-custommap] |
|---|---|
| [!DNL /sports/news/today.php] | 運動 |
| [!DNL /sports/products/buy.php] | 產品 |
| [!DNL /news/headlines.php] | 新聞 |
| [!DNL /news/products/subscribe.php] | 產品 |

輸出是根據查閱檔案中子字串的順序。 例如，cs-uri-stem會傳回 [!DNL /sports/products/buy.php] &quot;Products&quot;。 雖然URI乾開頭為&quot;/sports/&quot;，但字串&quot;/products/&quot;會列在查閱檔案中&quot;/sports/&quot;之前。 如果Multiple Values參數設為true，則x-custommap會有額外的值，因為最後一個範例會比對查閱表格中的兩列：產品與新聞。

## FlatFileLookup {#section-e09b2eeb96444a859b14f03cdaab31f2}

轉 [!DNL FlatFileLookup] 換使用由任意列數和行陣列成的查閱表（不過，請記得它駐留在記憶體中）。 在這種轉換期間，資料工作台伺服器依次讀取每個事件資料記錄，並將記錄中指定欄位的內容與查找表的指定列中的每個值進行比較。 如果存在匹配，則資料工作台伺服器將查找表中匹配行中的一個或多個值寫入事件資料記錄中的一個或多個指定輸出欄位。

此轉換期間使用的查閱表格會從您定義轉換時指定位置的平面檔案中填入。

<table id="table_772B8ABF3B44493F99069010DDB5F77A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設值 </td> 
   <td colname="col2"> 如果條件符合且查閱檔案中沒有項目符合輸入，則使用的預設值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用來分隔查閱檔案中欄的字串。 長度必須為單一字元。 </p> <p> 如果按住Ctrl鍵並在分隔字元參數內按一下滑鼠右鍵，則會出現「插入 <span class="wintitle"> 」功能表</span> 。 此功能表包含常用作分隔字元的特殊字元清單。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檔案 </td> 
   <td colname="col2"> 查閱檔案的路徑和檔案名稱。 相對路徑與資料工作台伺服器的安裝目錄有關。 此檔案通常位於資料工作台伺服器安裝目錄內的「查閱」目錄中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 標題列 </td> 
   <td colname="col2"> 是非。 指出表格中的第一列是要在處理中忽略的標題列。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> <span class="wintitle"> Column Name</span> （列名）是用於將輸入與檔案中的行匹配的列的名稱。 如果標題行為true，則可以是查閱檔案中欄的名稱。 否則，此欄數必須是零，才能符合。 <span class="wintitle"> 「欄位名稱</span> 」是用於尋找查閱檔案中列的欄位名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多重值 </td> 
   <td colname="col2"> <p>是非。 決定是否應傳回單一值（相符列）或多個值（每個相符列各一個）。 </p> <p> <p>注意： 如果 <span class="wintitle"> 「多個值</span> 」設為false，您必須確定沒有多個相符項目。 當發生多個相符項目時，無法保證會傳回哪個相符項目。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> <p>列對象（結果）的向量，其中每個對象由列名和欄位名定義。 </p> <p> <span class="wintitle"> 列名</span> 是從中獲取輸出值的列。 如果 <span class="wintitle"> 標題行</span> ，則可以是查閱檔案中欄的名稱。 否則，此欄數必須是零，才能符合。 </p> <p> <span class="wintitle"> 欄位名稱</span> (Field Name)是用來擷取輸出的欄位名稱。 請注意，這可以是結果的向量，在「多值」參數為true的情況下，每個列各標識一個向量。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

**注意事項[!DNL FlatFileLookup]**

* 將輸入欄位與查閱檔案比對時，一律須區分大小寫。
* 在檔案或檔案中定 [!DNL FlatFileLookup] 義的轉換中，若要變更查閱檔 [!DNL Transformation.cfg] 案， [!DNL Transformation Dataset Include] 必須重新轉換資料集。 在檔案或檔 [!DNL FlatFileLookup] 案中定義轉換的 [!DNL Log Processing.cfg] 查閱 [!DNL Log Processing Dataset Include] 檔案不受此限制。 如需重新處理資料的詳細資訊，請參 [閱重新處理和轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

* [!DNL FlatFileLookup] 檔案或檔案 [!DNL Log Processing.cfg] 中的轉換 [!DNL Log Processing Dataset Include] 會在查找檔案更改時重新載入其查找檔案。 更改不會追溯應用，但會應用於更改發生後讀取的所有日誌資料。

此範例說明如何使用轉換 [!DNL FlatFileLookup] 來整合查閱資料與從網站流量收集的事件資料。 假設您想要隔離將流量傳送至網站的網站合作夥伴，並將其合作夥伴ID轉換為更易用的名稱。 然後，您可以使用好用的名稱來建立延伸維度和視覺化，更清楚地對應至業務關係，而不是用於路由流量的網站對網站關係。

範例轉換會搜尋cs(referrer-query)欄位中的PartnerID名稱——值配對，如果找到，則會使用查閱檔案來比較PartnerID值與表格欄中 [!DNL Lookups\partners.txt][!DNL Partner] 的值。 如果找到行，則輸出欄位x-partner-name會從標識行的列 [!DNL PrintName] 中指定名稱。

![](assets/cfg_TransformationType_FlatFileLookup.png)

如果查閱表格包含下列資訊：

| ID | Partner | 已開始 | PrintName |
|---|---|---|---|
| 1 | P154 | 1999年8月21日 | Yahoo |
| 2 | P232 | 2000 年 7 月 10 日 | Microsoft |
| 3 | P945 | 2001年1月12日 | 亞馬遜 |

以下範例會轉換如下：

* 如果cs(referrer)(PartnerID)傳回P232，則欄位x-partner-name會被指定為&quot;Microsoft&quot;。
* 如果cs(referrer)(PartnerID)傳回P100，則欄位x-partner-name會被指定為「無合作夥伴」。
* 如果cs(referrer)(PartnerID)未傳回任何內容，則欄位x-partner-name會依預設參數指定為「無合作夥伴」值。

## ODBCLookup {#section-4dcc3747e42e45c0a057e85f308a83cc}

轉 [!DNL ODBCLookup] 型就像轉 [!DNL FlatFileLookup] 型。 唯一的區別是，在此轉換期間使用的查找表是從ODBC資料庫而不是平面檔案中填充的。

>[!NOTE]
>
>[!DNL ODBCLookup] 轉換只能在資料集構建過程的轉換階段執行。 如果可能，Adobe建議您使用轉 [!DNL FlatFileLookup] 換，而非轉 [!DNL ODBCLookup] 換。 [!DNL FlatFileLookup] 轉換在本質上更可靠，因為它們不依賴於外部系統的可用性。 此外，如果查閱表格位於您控制本機的平面檔案中，則修改該表格的風險較低。

<table id="table_B903DB291BCC4F44B09D54300216D288"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料來源名稱 </td> 
   <td colname="col2"> DSN由資料工作台伺服器機器的管理員提供，其中資料集被處理在該伺服器機器上，該DSN是指要從其載入資料的資料庫。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫口令 </td> 
   <td colname="col2">連接資料庫時要使用的口令。 如果已在「 <span class="wintitle"> Data Source Administrator（資料源管理員）」中為DSN配置了密碼</span>，則此密碼可能保留為空。 此處提供的任何口令將覆蓋「資料源管理員」中為DSN配置 <span class="wintitle"> 的口令</span>。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 資料庫用戶ID </td> 
   <td colname="col2">連接資料庫時要使用的用戶ID。 如果已在「 <span class="wintitle"> Data Source Administrator（資料源管理員）」中為DSN配置了用戶ID</span>，則此ID可能保留為空。 此處提供的任何用戶ID將覆蓋「資料源管理員」中為DSN配置的 <span class="wintitle"> 用戶ID</span>。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設值 </td> 
   <td colname="col2"> 如果條件符合且查閱檔案中沒有項目符合輸入，則使用的預設值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入欄 </td> 
   <td colname="col2"> <span class="wintitle"> Column Name</span> （列名）是與輸入匹配的資料的列名或SQL表達式。 <span class="wintitle"> 「欄位名稱</span> 」是包含要查閱之資料之欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 多重值 </td> 
   <td colname="col2"> <p>是非。 決定是否應傳回單一值（相符列）或多個值（每個相符列各一個）。 </p> <p> <p>注意： 如果 <span class="wintitle"> 「多個值</span> 」設為false，您必須確定沒有多個相符項目。 當發生多個相符項目時，無法保證會傳回哪個相符項目。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出欄 </td> 
   <td colname="col2"> <p>列對象（結果）的向量，其中每個對象由列名和欄位名定義。 </p> <p> <span class="wintitle"> 列名</span> 是從中獲取輸出值的列的名稱或SQL表達式。 <span class="wintitle"> 欄位名稱</span> (Field Name)是用來擷取輸出的欄位名稱。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 表格識別碼</span> </td> 
   <td colname="col2"> 一個SQL表達式，它命名要從中載入資料的表或視圖。 典型表標識符的格式為SCHEMA.TABLE。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

* 資料源名 [!DNL Database User ID]稱、 [!DNL Database Password]和表標識符參數與ODBC資料源描述的相同名稱的參數相同。 See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

* 與ODBC資料源不同， [!DNL ODBCLookup] 轉換不需要增加的ID列。 See [ODBC Data Sources](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3). 這是因為當資料集作用中時，查閱表格的內容不得以任何方式變更。 在重新轉換發生之前，無法偵測到查閱表格或檢視中的變更。 如需重新處理資料的詳細資訊，請參 [閱重新處理和轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。

假設您想將過時的DNS記錄轉換為更新的記錄。 這兩組記錄都儲存在SQL資料庫中。 要執行此任務，您將引用從資料庫生成的查找表並替換過期的DNS記錄。

我們的示例轉換搜索s-dns欄位的日誌條目，如果找到，則使用查找表VISUAL.LOOKUP將s-dns條目與表列中的條目 [!DNL OLDDNS] 進行比較。 如果行位於表中，則輸出欄位s-dns會從所標識行的列獲得更 [!DNL NEWDNS] 新的DNS記錄條目。

![](assets/cfg_TransformationType_ODBCLookup.png)

