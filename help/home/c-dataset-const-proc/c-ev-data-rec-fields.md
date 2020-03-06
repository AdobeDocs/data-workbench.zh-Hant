---
description: 資料工作台伺服器可處理的資料欄位相關資訊，以建立資料集。
solution: Analytics
title: 事件資料記錄欄位
topic: Data workbench
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 事件資料記錄欄位{#event-data-record-fields}

資料工作台伺服器可處理的資料欄位相關資訊，以建立資料集。

* [關於事件資料](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [基線事件資料記錄欄位](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [衍生欄位](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## 關於事件資料 {#section-3a0705f8c1824017aa4effed9903efbe}

用於建立資料集的事件資料位於稱為記錄來源的檔案中。 日誌源中可用的資料稱為事件資料，因為每個資料記錄都表示事務記錄或具有關聯時間戳記的事件的單個實例。

日誌源的事件資料由即時收集 [!DNL Sensors]。 從HTTP和應用程 [!DNL Sensors] 式伺服器收集的事件資料會傳送至資料工作台伺服器，以將資料轉換為壓縮的記錄檔( [!DNL .vsl])檔案。 資料工作台伺服器讀取駐留在平面檔案、XML檔案或ODBC資料源中的事件資料，該伺服器提供瞭解碼器，您可以定義解碼器，以便從這些不同格式中抽取一組通用資料欄位。

以下各節提供資料工作台伺服器所收集或讀取並可用的資料欄位(稱為事件資料記錄欄位或記錄項目欄 [!DNL Sensors] 位)相關資訊。

>[!NOTE]
>
>欄位名稱通常遵循W3C擴充記錄檔格式的命名慣例。 許多欄位的前置詞都指示欄位中包含的資訊的來源：

* cs表示從用戶端到伺服器的通訊。
* sc表示從伺服器到客戶端的通信。
* s表示來自伺服器的資訊。
* c表示來自客戶端的資訊。
* x表示由Adobe軟體產品建立的資訊。

## 基線事件資料記錄欄位 {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

記錄檔( [!DNL .vsl])檔案包含事件資料欄位，這些欄位是資料集建構程式中資料工作台 [!DNL Sensors] 伺服器從伺服器收集並使用的事件資料。 下表列出由記錄的典型事件資料記錄中的欄位 [!DNL Sensor]:

<table id="table_98E135FE4EAF44D6ADEB3C6C1C0BF6A4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> <p>向伺服器發出請求時包含的客戶機的IP地址。 </p> <p> 例如: 207.68.146.68 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> <p>用戶端隨請求傳送的Cookie。 </p> <p> 範例：v1st=42FDF66DE610CF36;ASPSESSIONIDQCATDAQC=GPIBKEIBFFIPLOJMKAAEPM; </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> <p>用戶端透過請求傳送至伺服器的HTTP反向連結字串。 </p> <p> 範例： <span class="filepath"> http://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> <p>由客戶端發送的字串及其向伺服器發出的請求，該字串指示客戶端的用戶代理類型。 </p> <p> 範例：Mozilla/5.0(Windows;U;Windows NT 5.1;en-US;rv:1.7)Gecko/20040707 Firefox/0.9.2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-method </td> 
   <td colname="col2"> <p>HTTP請求的方法類型。 </p> <p> 範例：取得 </p> <p> 參考： <span class="filepath"> http://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> <p>URI的查詢字串部分（stem +查詢字串= URI）。 此前會加上問號(?)且可包含一或多個名稱值對，並以&amp;符號(&amp;)分隔。 </p> <p> 範例：page=homepage </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> <p>URI的莖部（莖+查詢字串= URI）。 乾是伺服器上請求資源的實際或邏輯路徑。 </p> <p> 範例： <span class="filepath"> /index.asp </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> <p>由伺服器報告的客戶端請求的資源的內容類型。 </p> <p> 範例：text/html, image/png, image/gif, video/mpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-bytes </td> 
   <td colname="col2"> <p>響應請求從伺服器發送到客戶端的資料位元組數 </p> <p> 例如: 4996 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> <p>伺服器返回給客戶端的狀態代碼。 </p> <p> 例如: 200 </p> <p> 參考： <span class="filepath"> http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> <p>所請求資源主機的完全限定域名或IP地址。 </p> <p> 範例： <span class="filepath"> www.adobe.com </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-experient </td> 
   <td colname="col2"> <p>請求時客戶端所屬的所有受控實驗名稱和組的清單。 </p> <p> 範例：VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestamp </td> 
   <td colname="col2"> <p>伺服器收到請求的日期和時間(GMT)。 時間以1600年1月1日以來的100納秒數表示。 </p> <p> 範例：127710989320000000是2005年9月13日星期二11:28:52.00000的x-timestamp值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> <p>由感測器設定、由用戶端向伺服器提供之永久性Cookie中所找到之唯一瀏覽器識別碼的64位元 <span class="wintitle"></span> 十六進位值。 </p> <p> 範例：42FDF66DE610CF36 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 衍生欄位 {#section-b6c57ee2aa31469fbd5dab90e52bc677}

下表列出資料工作台伺服器從基準事件資料記錄欄位衍生的欄位範例：

<table id="table_3B008F1314804A69AE69E8F94908F497"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> cs(cookie)(name) </td> 
   <td colname="col2"> Cookie中指定名稱值對的值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-domain) </td> 
   <td colname="col2"> <p>HTTP反向連結URI的網域名稱或IP位址。 </p> <p> <p>注意： 此欄位為唯讀。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-host) </td> 
   <td colname="col2"> <p>反向連結的整個主機名稱。 </p> <p> 範例：如果cs(referrer)是 <span class="filepath"> http://my.domain.com/my/page </span>，則cs(referrer-host) <span class="filepath"> 是my.domain.com </span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer-query)(name) </td> 
   <td colname="col2"> <p>反向連結查詢字串的值。 </p> <p> <p>注意： 您無法使用cs(referrer)(name)欄位存取反向連結查詢字串值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri </td> 
   <td colname="col2"> <p>完整的URI（stem +查詢字串=整個URI）。 </p> <p> 範例： <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query(name) </td> 
   <td colname="col2"> <p>與給定名稱關聯的值。 如果給定名稱存在多個值，則此欄位返回這些值中的最後一個值。 </p> 範例： 
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B"> 
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> 對於URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>, cs-uri-query(product3)將會傳回cd。 </li> 
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> 對於URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"></span> cs-uri-query(product1)會傳回casette。 </li> 
    </ul> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ctime </td> 
   <td colname="col2"> x-timestamp表示自1970年1月1日以來的秒數。 此欄位也稱為x-unixtime。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> date </td> 
   <td colname="col2"> 格式為YYYY-MM-DD的x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間 </td> 
   <td colname="col2"> 格式為HH:MM:SS的x-timestamp。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-local-timestring </td> 
   <td colname="col2"> <p>x-timestamp已轉換為資料集的 <span class="filepath"> Transformation.cfg檔案中指定的本 </span> 機時區。 格式為YYYY-MM-DD HH:MM:SS.mmm。 </p> <p> <p>注意： 您也可以在「記錄處理。cfg」檔案中定義時間轉換，例如x <span class="filepath"> -local-timestring </span> 。 如需詳細資訊，請參 <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 閱記錄處理設定檔 </a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-log-source-id </td> 
   <td colname="col2"> <p>與特定日誌條目的日誌源對應的標識符。 對於要記錄的標識符，在定義感測器、日誌檔案或ODBC資料源時，必須在 <span class="wintitle"> Log Processing.cfg檔案的「日誌源ID」(Log Source ID)欄位中指定該 </span><span class="filepath"></span><span class="wintitle"></span>標識符。 如需詳細資訊，請參 <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 閱記錄處理設定檔 </a>。 </p> <p> 範例：從VSensor01。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-mask </td> 
   <td colname="col2"> 感測器資料源的 <span class="wintitle"> 掩碼 </span> 模式(從。vsl檔案 <span class="filepath"> 名派生 </span> )。 對於名稱格式為 <span class="filepath"> YYYYMMDD-SENSORID.VSL的檔案 </span>,x-mask為SENSORID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-timestring </td> 
   <td colname="col2"> 格式為YYYY-MM-DD的x-timestamp HH:MM:SS.mm。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> x-unixtime </td> 
   <td colname="col2"> 從x-timestamp衍生的十進位UNIX時間。 </td> 
  </tr> 
 </tbody> 
</table>

[!DNL Sensor]，當用於伺服器時，可以透過伺服器的API，從任何有效的HTTP要求或回應標題或變數收集事件資料欄位。 若要收集此類資料欄位，您必須在設定檔中指定所要的標題欄位 [!DNL txlogd.conf]或變數 [!DNL Sensor]。 For more information, see the *Data Workbench[!DNL Sensor]Guide*.
