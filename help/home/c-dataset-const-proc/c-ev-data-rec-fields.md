---
description: Data Workbench伺服器可處理以建立資料集之資料欄位的相關資訊。
title: 事件資料記錄欄位
uuid: b0232bfa-0a3b-4e3d-876e-6a15a3764eae
exl-id: 35433b87-991a-4fb9-ba6a-3217e89eb769
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 2%

---

# 事件資料記錄欄位{#event-data-record-fields}

Data Workbench伺服器可處理以建立資料集之資料欄位的相關資訊。

* [關於事件資料](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-3a0705f8c1824017aa4effed9903efbe)
* [基線事件資料記錄欄位](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-a882ed7aa6af41eeb45a55bf8c1ca3d7)
* [衍生欄位](../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#section-b6c57ee2aa31469fbd5dab90e52bc677)

## 關於事件資料 {#section-3a0705f8c1824017aa4effed9903efbe}

用來建立資料集的事件資料位於稱為記錄來源的檔案中。 記錄來源中可用的資料稱為事件資料，因為每個資料記錄代表交易記錄或具有相關時間戳記之事件的單一例項。

[!DNL Sensors]即時收集日誌源的事件資料。 由[!DNL Sensors]從HTTP和應用程式伺服器收集的事件資料會傳送至Data Workbench伺服器，這些伺服器會將資料轉換為壓縮的記錄檔([!DNL .vsl])檔案。 一般檔案、XML檔案或ODBC資料來源中的事件資料由Data Workbench伺服器讀取，該伺服器提供您定義的解碼器，以便從這些不同格式中擷取一般資料欄位集。

以下小節提供由[!DNL Sensors]收集或讀取並提供給Data Workbench伺服器使用的資料欄位（稱為事件資料記錄欄位或記錄項目欄位）的相關資訊。

>[!NOTE]
>
>欄位名稱通常會遵循W3C擴充記錄檔格式的命名慣例。 許多欄位的前置詞都表示欄位中包含的資訊的來源：

* cs表示從客戶端到伺服器的通信。
* sc指示從伺服器到客戶端的通信。
* s表示來自伺服器的資訊。
* c指示來自客戶端的資訊。
* x表示由Adobe軟體產品建立的資訊。

## 基線事件資料記錄欄位 {#section-a882ed7aa6af41eeb45a55bf8c1ca3d7}

記錄檔([!DNL .vsl])檔案包含由[!DNL Sensors]從伺服器收集，並由Data Workbench伺服器在資料集建構程式中使用的事件資料欄位。 下表列出由[!DNL Sensor]記錄的典型事件資料記錄中的欄位：

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
   <td colname="col2"> <p>向伺服器發出的請求中包含的客戶端的IP地址。 </p> <p> 例如: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>用戶端隨請求傳送的Cookie。 </p> <p> 範例：v1st=42FDF66DE610CF36;ASPSESSIONIDQCATDAQC=GPIBKEIBFFIPLOJMKCAAEPM; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>由用戶端隨請求傳送至伺服器的HTTP反向連結字串。 </p> <p> 範例：<span class="filepath"> https://www.mysite.net/cgi-bin/websearch?qry </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>由客戶端發送的字串及其向伺服器的請求，該字串指示客戶端的用戶代理類型。 </p> <p> 範例：Mozilla/5.0(Windows;U;Windows NT 5.1;美國；rv:1.7)Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>HTTP要求的方法類型。 </p> <p> 範例：GET </p> <p> 參考資料：<span class="filepath"> https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>URI的查詢字串部分（stem +查詢字串= URI）。 前面有問號(?) 且可包含一或多個以&amp;符號分隔的名稱值組。 </p> <p> 範例：page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> <p>URI的幹部分（乾+查詢字串= URI）。 乾是伺服器上請求資源的實際路徑或邏輯路徑。 </p> <p> 範例：<span class="filepath"> /index.asp </span> </p> </td>
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
   <td colname="col2"> <p>伺服器返回給客戶端的狀態代碼。 </p> <p> 例如: 200 </p> <p> 參考資料：<span class="filepath"> https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>所請求資源的主機的完全限定的域名或IP地址。 </p> <p> 範例：<span class="filepath"> www.adobe.com </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x實驗 </td>
   <td colname="col2"> <p>請求時客戶端所屬的所有受控實驗名稱和組的清單。 </p> <p> 範例：VSHome_Exp.Group_1,VSRegistration_Exp.Group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>伺服器收到請求的日期和時間(GMT)。 時間以1600年1月1日以來的100納秒數表示。 </p> <p> 範例：127710989320000000會是2005年9月13日星期二11:28:52.0000000的x-timestamp值。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>由<span class="wintitle">感測器</span>設定、由客戶端向伺服器提供的、在永久Cookie中找到的唯一瀏覽器標識符的64位十六進位值。 </p> <p> 範例：42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

## 衍生欄位 {#section-b6c57ee2aa31469fbd5dab90e52bc677}

下表列出Data Workbench伺服器從基準事件資料記錄欄位衍生的欄位範例：

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
   <td colname="col2"> Cookie內指定名稱值組的值。 </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-domain) </td>
   <td colname="col2"> <p>HTTP反向連結URI的域名或IP地址。 </p> <p> <p>注意： 此欄位為唯讀欄位。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-host) </td>
   <td colname="col2"> <p>反向連結的整個主機名稱。 </p> <p> 範例：如果cs(referrer)為<span class="filepath"> https://my.domain.com/my/page </span>，則cs(referrer-host)為<span class="filepath"> my.domain.com </span>。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer-query)(name) </td>
   <td colname="col2"> <p>反向連結查詢字串的值。 </p> <p> <p>注意： 您無法使用cs(referrer)(name)欄位存取反向連結查詢字串值。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri </td>
   <td colname="col2"> <p>完整的URI（stem +查詢字串=整個URI）。 </p> <p> 範例：<span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query(name) </td>
   <td colname="col2"> <p>與指定名稱相關聯的值。 如果指定名稱有多個值，此欄位會傳回這些值的最後一個。 </p> 範例：
    <ul id="ul_47BBB2E3076A46629BFCDB2A460F700B">
     <li id="li_AC9BB29505A54AE4AFF49438530C9EA4"> 對於URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product2=casette&amp;product3=cd </span>,cs-uri-query(product3)將返回cd。 </li>
     <li id="li_B036C1D0B25748E0A155DDC9B1B999CB"> 對於URI <span class="filepath"> /shopping/checkout.html?product1=8Track&amp;product1=casette </span>, <span class="wintitle"> cs-uri-query(product1)</span>將返回casette。 </li>
    </ul> <p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> ctime </td>
   <td colname="col2"> x-timestamp以自1970年1月1日起的秒數表示。 此欄位也稱為x-unixtime。 </td>
  </tr>
  <tr>
   <td colname="col1"> 日期 </td>
   <td colname="col2"> x-timestamp，格式為YYYY-MM-DD。 </td>
  </tr>
  <tr>
   <td colname="col1"> 時間 </td>
   <td colname="col2"> 格式為HH:MM:SS的x-timestamp。 </td>
  </tr>
  <tr>
   <td colname="col1"> x-local-timestring </td>
   <td colname="col2"> <p>x-timestamp轉換為資料集<span class="filepath"> Transformation.cfg </span>檔案中指定的本機時區。 格式為YYYY-MM-DD HH:MM:SS.mm。 </p> <p> <p>注意： 您也可以在<span class="filepath"> Log Processing.cfg </span>檔案中定義時間轉換，例如x-local-timestring。 有關資訊，請參閱<a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">日誌處理配置檔案</a>。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-log-source-id </td>
   <td colname="col2"> <p>與特定日誌條目的日誌源對應的標識符。 要記錄的標識符，在定義<span class="wintitle">感測器</span>、日誌檔案或ODBC資料源時，必須在<span class="filepath"> Log Processing.cfg </span>檔案的<span class="wintitle"> Log Source ID </span>欄位中指定。 如需詳細資訊，請參閱<a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">記錄處理組態檔</a>。 </p> <p> 範例：來自VSensor01。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x遮色片 </td>
   <td colname="col2"> <span class="wintitle">感測器</span>資料源的掩碼模式（從<span class="filepath"> .vsl </span>檔案名派生）。 對於名稱為<span class="filepath"> YYYYYMMDD-SENSORID.VSL </span>格式的檔案，x-mask為SENSORID。 </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestring </td>
   <td colname="col2"> x-timestamp格式，格式為YYYY-MM-DD HH:MM:SS.mm。 </td>
  </tr>
  <tr>
   <td colname="col1"> x-unixtime </td>
   <td colname="col2"> 從x-timestamp衍生的十進位UNIX時間。 </td>
  </tr>
 </tbody>
</table>

[!DNL Sensor]，在伺服器上使用時，可透過伺服器的API，從任何有效的HTTP要求或回應標題或可用的變數中收集事件資料的欄位。要收集此類資料欄位，必須在[!DNL txlogd.conf]配置檔案中為[!DNL Sensor]指定所需的標題欄位或變數。 如需詳細資訊，請參閱&#x200B;*Data Workbench[!DNL Sensor]指南*。
