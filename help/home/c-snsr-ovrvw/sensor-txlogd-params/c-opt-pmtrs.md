---
description: 有關可選感測器txtlogd.conf檔案參數的資訊。
solution: Insight
title: 可選參數
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Optional Parameters{#optional-parameters}

有關可選感測器txtlogd.conf檔案參數的資訊。

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> AddressFilter </td> 
   <td colname="col2"> <p>可讓您篩選指定的IP位址。 </p> <p>當您篩選特定位址時，不會記錄「封包」。 此功能在日誌處理之前消除了內部或受監控的代理，從而提高了日誌處理的速度並降低了資料儲存要求。 在指定地址時，可以使用通配符。 </p> <p>範例：地 <span class="filepath"> 址篩選器10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>指定是否在記錄中包含或排除某些類型的內容。 </p> <p>參數值與回覆的內容類型進行首碼比對。 </p> <p>例如，"image/"與所有影像內容類型相符，而"image/gif"則只與該類型相符。 當特定內容類型發生多個比對時，會使用最特定的比對。 因此，您可以在ContentFilterInclude參數中加上"image/gif"，在ContentFilterExclude參數中加上"image/gif"，並允許「image/gif」回覆，但會篩選掉所有其他影像類型。 </p> <p>範例： <span class="filepath"> ContentFilterInclude *</span> </p> <p>範例： <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時才設定此參數。 </p> <p>啟用Web模組和發射器的調試記錄。 </p> <p>當感測器無法正確工作 <span class="wintitle"> 時</span> ，可使用此參數。 設定此參數後，您必須在指定的路徑位置建立空白檔案，並為所有使用者提供「寫入」權限。 例如（在Web伺服器上的unix殼層內）: 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>您只應在短時間內啟用除錯記錄，之後應將記錄檔傳送至Adobe諮詢服務進行分析。 </p> <p>範例： <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe建議您先在測試環境中設定此參數，以判斷對您系統的影響。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DisableField </td> 
   <td colname="col2"> <p>停用指定欄位 </p> <p>使用者可移除他們不使用或不想儲存的欄位。 如果欄位取得字串值，停用欄位會傳遞空白字串。 如果欄位取數值，停用欄位會傳遞數字零(0)。 您可以停用下列欄位： 
     <ul id="ul_4537B345EFAE449A9946DA0B52EA5C43"> 
      <li id="li_D674BC1982344C49B25A73EFF095C34A">sc-status </li> 
      <li id="li_6D647C845EB54B1B84C756DCDD7DD4CC">x-new-visitor </li> 
      <li id="li_65EB695B223040BCB9888375354B6E8B">x-trackingid </li> 
      <li id="li_41197A9CB961496B9CD26AA8457233FD">sc-bytes </li> 
      <li id="li_DCD45D7E21964B959299494FA719F453">c-ip </li> 
      <li id="li_7650796C6246484C8267ED9923596AFB">cs-method </li> 
      <li id="li_8941FCBBAA5E42EA9F04DA06EB91CAC5">cs-uri-stem </li> 
      <li id="li_A10438D2DEBB4ADFB574BF7094F9F0C4">cs-uri-query </li> 
      <li id="li_1D83BA59AC8543319D1966BB8ED1D931">s-dns </li> 
      <li id="li_34A23CE1944F4AEFBE7D74E8D6D5BEE6">cs(referrer) </li> 
      <li id="li_B85D93C381BD440F82C711C9A6D56CE9">cs(cookie) </li> 
      <li id="li_18D9C084450149D6A8713EBDA0C02E5B">cs(user-agent) </li> 
      <li id="li_A175CAF03E51473E990BE4F31F198B42">cs(useragent) </li> 
      <li id="li_ED38ED31B2644F2FA1C86FF93ADB9CEF">sc(content-type) </li> 
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x-experient </li> 
     </ul> </p> <p>範例： <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>控制實驗配置檔案的路徑。 </p> <p>範例：ExpFile <span class="filepath"> C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>在請求時產生新追蹤ID並將使用者放入實驗群組的資源。 </p> <p> <p>注意： 此資源不必在Web伺服器上實際存在。 </p> </p> <p>範例： <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>如果要啟用受控實驗將整個站點或站點的整個子目錄重新映射到另一個位置，請將此參數設定為「on」。預設值為「off」。 </p> <p>範例：關 <span class="filepath"> 閉ExpPartialMatch</span> </p> <p> <p>注意： 將此參數設為「on」時請務必小心。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>即使使用者要求ContentFilterExclude參數篩選出的檔案類型，也可判斷是否記錄每位新使用者的首次點按。 </p> <p>預設值為"no"。 </p> <p>通常，影像檔案會由ContentFilterExclude參數篩選掉。 如果LogAllNewUsers設為"yes"，而新使用者從伺服器取得的第一個檔案就是影像，則會記錄該要求。 如果LogAllNewUsers參數設為"no"或完全未設定（並假設影像已由ContentFilterExclude參數篩選出），而新使用者從伺服器取得的第一份檔案就是影像，則不會記錄該要求。 </p> <p>範例： <span class="filepath"> LogAllNewUsers否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>發送器等待發送下一批資料包的秒數。 </p> <p>預設值為 15。 </p> <p>範例： <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>注意： 請先聯絡Adobe諮詢服務，才要變更此參數值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱私權ID </td> 
   <td colname="col2"> <p>可讓您停用訪客追蹤，以便用來符合退出原則。 </p> <p>啟用後， <span class="wintitle"> Sensor</span> （感測器）不會為其V1st Cookie設為指定PrivacyID的任何訪客記錄「資料包」。 由於沒有記錄這些訪客的資訊，因此這些訪客的相關資訊不會傳送至資料工作台伺服 <span class="keyword"> 器進行處理</span> 。 </p> <p>若要啟用此功能，您必須完成下列步驟： 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID必須在感測器的txlogd.conf檔案中定 <span class="filepath"> 義為0(零</span> ) <span class="wintitle"> 值</span>。 <p>範例： <span class="filepath"> 隱私權ID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">網站擁有者必須編寫程式碼來設定訪客(V1st)Cookie，使Cookie ID值符合定義為"<span class="filepath"> txlogd.conf</span>"的PrivacyID值。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>發射器(txlogd)定期傳送請求的位置，以查看網站是否正常運作。 </p> <p>請注意，位置是以下列格式指定，而非URL: </p> <p>http,<i>serverAddress, port,/resource</i> </p> <p>其中 <i>serverAddress</i> 是伺服器名稱或IP位址，port <i>是伺服器的HTTP監聽埠，</i><i></i> resource是要請求的特定資源（可包含查詢字串）。 </p> <p>您可以指定多個SiteTest行。 </p> <p>範例： <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>注意： 目前僅支援http。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>訪客瀏覽器上設定的Cookie名稱。 </p> <p>預設值為"v1st"。 </p> <p>範例： <span class="filepath"> 追蹤Cookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>指示是否根據CertName參數驗證伺服器 </p> <p>預設值為「開啟」。 </p> <p>範例： <span class="filepath"> VerifyCertName on</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_598C3CDA5AA440228AF88C3BE4A8F77C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ISCaptureBytesSent </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時才設定此參數。 </p> <p>告知IIS <span class="wintitle"> Sensor</span> （IIS感測器），應該使用哪兩個可能的日誌記錄「掛接」來記錄資料包 </p> <p>當IIS感測器未正確記錄 <span class="wintitle"> 資料包時</span> ，請使用此參數。 如果預設記錄掛接無法正常運作，此參數會設為「off」。 預設值為「開啟」。 </p> <p>範例： <span class="filepath"> ISCaptureBytesSent on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時才設定此參數。 </p> <p>告訴 <span class="wintitle"> Sensor</span> （感測器）應使用哪兩個可能的"hook"來設定v1st Cookie。 </p> <p>當IIS Sensor <span class="wintitle"></span> not setting the v1st Cookie（IIS感測器未正確設定v1st Cookie）時，可使用此參數。 如果預設的掛接未正確設定v1st Cookie，此參數會設為"yes"。 預設值為"no"。 </p> <p>範例： <span class="filepath"> IISUseAlternateHandler否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>預設情況下， <span class="wintitle"> Sensor</span> 會在每個請求上發送快取控制響應標頭。 啟用快取控制功能後， <span class="wintitle"> Sensor</span> （感測器）會向瀏覽器發送一個「Expires」（過期）報頭，其值為Thu, 1994年12月1日16:00:00 GMT。 </p> <p>您可以視需要在txlogd.conf檔案中編輯以下兩行，以修改 <span class="filepath"> 響應字串</span> : </p> <p> <span class="filepath"> NewUserCacheControl</span><i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span><i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>範例： </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl專用，max-age=0,must-revalidate</span> </p> <p>若要停用快取控制回應標頭的傳送，請為每一行輸入連字型大小，如下所示： </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_88696CCA93874BB683538BD614E07890"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此參數中…… </th> 
   <th colname="col2" class="entry"> 指定分類的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時才設定此參數。 </p> <p>告訴 <span class="wintitle"> Sensor</span> （感測器）應使用哪兩個可能的"hook"來設定v1st Cookie。 </p> <p>當Apache感測器未正確設 <span class="wintitle"> 定v1st Cookie時</span> ，請使用此參數。 如果預設的掛接未正確設定v1st Cookie，此參數會設為"yes"。 預設值為"no"。 </p> <p>範例： <span class="filepath"> ApacheUseAlternateHandler否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時才設定此參數。 </p> <p>指示傳 <span class="wintitle"> 感器</span> ，嘗試在兩個掛接中設定v1st Cookie。 </p> <p>當Apache感測器未正確設 <span class="wintitle"> 定v1st Cookie時</span> ，請使用此參數。 預設值為"yes"。 </p> <p>如果設為"yes"，而v1st Cookie未在第一個掛接中正確設定，則會使用第二個掛接。 如果設為"no"，您會設定ApacheUseAlternateHandler參數，以指出要用來設定v1st Cookie的掛接。 </p> <p>範例： <span class="filepath"> ApacheUseBothHandlersyes</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>預設情況下， <span class="wintitle"> Sensor</span> 會在每個請求上發送快取控制響應標頭。 啟用快取控制功能後， <span class="wintitle"> Sensor</span> （感測器）會向瀏覽器發送一個「Expires」（過期）報頭，其值為Thu, 1994年12月1日16:00:00 GMT。 </p> <p>您可以視需要在txlogd.conf檔案中編輯以下兩行，以修改 <span class="filepath"> 響應字串</span> : </p> <p> <span class="filepath"> NewUserCacheControl</span><i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span><i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>範例： </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl專用，max-age=0,must-revalidate</span> </p> <p>若要停用快取控制回應標頭的傳送，請為每一行輸入連字型大小，如下所示： </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>注意： Adobe建議您不要停用此功能。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_BF01F6265B8544DA9D9AD2C80A64C0F3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 在此參數中…… </th> 
   <th colname="col2" class="entry"> 指定分類的... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> ApacheUseAlternateHandler </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時才設定此參數。 </p> <p>告訴 <span class="wintitle"> Sensor</span> （感測器）應使用哪兩個可能的"hook"來設定v1st Cookie。 </p> <p>當Apache感測器未正確設 <span class="wintitle"> 定v1st Cookie時</span> ，請使用此參數。 如果預設的掛接未正確設定v1st Cookie，此參數會設為"yes"。 預設值為"no"。 </p> <p>範例： <span class="filepath"> ApacheUseAlternateHandler否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時才設定此參數。 </p> <p>指示傳 <span class="wintitle"> 感器</span> ，嘗試在兩個掛接中設定v1st Cookie。 </p> <p>當Apache感測器未正確設 <span class="wintitle"> 定v1st Cookie時</span> ，請使用此參數。 預設值為"yes"。 </p> <p>如果設為"yes"，而v1st Cookie未在第一個掛接中正確設定，則會使用第二個掛接。 如果設為"no"，您會設定ApacheUseAlternateHandler參數，以指出要用來設定v1st Cookie的掛接。 </p> <p>範例： <span class="filepath"> ApacheUseBothHandlersyes</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

