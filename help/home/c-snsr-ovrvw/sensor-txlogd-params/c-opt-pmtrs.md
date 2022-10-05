---
description: 有關可選Sensor txlogd.conf檔案參數的資訊。
title: 選用參數
uuid: 8515a571-93ce-49cd-9ded-c9273259d0ee
exl-id: 5141f215-979c-4eb8-8c2c-94eef5815743
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1484'
ht-degree: 1%

---

# 選用參數{#optional-parameters}

{{eol}}

有關可選Sensor txlogd.conf檔案參數的資訊。

<table id="table_5FF491A7A6C24E43A06A5C344BF05430"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 地址篩選 </td> 
   <td colname="col2"> <p>可讓您篩選指定的IP位址。 </p> <p>篩選特定地址時，不會記錄「封包」。 該功能在日誌處理之前消除了內部或被監視的代理，從而提高了日誌處理的速度並降低了資料儲存要求。 在指定地址時，可以使用通配符。 </p> <p>範例： <span class="filepath"> 地址篩選器10.0.0.000</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ContentFilterInclude </p> <p>ContentFilterExclude </p> </td> 
   <td colname="col2"> <p>指定是否要在記錄中包含或排除特定類型的內容。 </p> <p>參數值會與回覆的內容類型進行前置詞比對。 </p> <p>例如，「image/」符合所有影像內容類型，而「image/gif」僅符合該類型。 當指定內容類型發生多個符合時，會使用最具體的符合。 因此，您可以將"image/gif"放在ContentFilterInclude參數中，將"image/gif"放在ContentFilterExclude參數中，並允許"image/gif"答復，但會過濾掉所有其他影像類型。 </p> <p>範例： <span class="filepath"> ContentFilterInclude *</span> </p> <p>範例： <span class="filepath"> ContentFilterExclude image/,text/css,application/x-javascript</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> DebugLogPath </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時，才設定此參數。 </p> <p>為Web模組和傳送器啟用除錯記錄。 </p> <p>您可在 <span class="wintitle"> 感測器</span> 無法正常運作。 設定此參數後，您必須在指定的路徑位置建立空檔案，並為所有使用者授予「寫入」權限。 例如（Web伺服器上的unix殼層內）: 
     <ul id="ul_7A067014A78048BF9D2F23DC66FF9E24"> 
      <li id="li_11C51EB9B9CC431585ECE9E8648F6122"><span class="filepath"> % cd /var/log</span> </li> 
      <li id="li_C56B2B5D49A543DBB258C5DE099B4AE5"><span class="filepath"> % touch vslog.txt</span> </li> 
      <li id="li_DA914383F813453AB6EF4F89279FD786"><span class="filepath"> % chmod a+w vslog.txt</span> </li> 
     </ul> </p> <p>您只應在短時間內啟用除錯記錄，之後應將記錄檔傳送至Adobe諮詢服務進行分析。 </p> <p>範例： <span class="filepath"> DebugLogPath /var/log/vslog.txt</span> </p> <p>Adobe建議先在測試環境中設定此參數，以判斷對您系統的影響。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 禁用欄位 </td> 
   <td colname="col2"> <p>禁用指定的欄位 </p> <p>使用者可以消除不使用或不想儲存的欄位。 如果欄位取用字串值，停用此欄位會傳遞空白字串。 如果欄位採用數值，則禁用該欄位將傳遞數字零(0)。 您可以停用下列欄位： 
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
      <li id="li_1173C0027C8A4638BDF35E9719CD9D4C">x實驗 </li> 
     </ul> </p> <p>範例： <span class="filepath"> DisableField x-trackingid</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpFile </td> 
   <td colname="col2"> <p>受控實驗配置檔案的路徑。 </p> <p>範例： <span class="filepath"> ExpFile C:\VisualSensor\experiment.txt</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpCookieURL </td> 
   <td colname="col2"> <p>當請求時，會產生新追蹤ID並將使用者放入實驗群組的資源。 </p> <p> <p>注意：此資源不必實際存在於Web伺服器上。 </p> </p> <p>範例： <span class="filepath"> ExpCookieURL /setcookie.htm</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ExpPartialMatch </td> 
   <td colname="col2"> <p>如果您想要啟用受控實驗，將您整個網站或網站的整個子目錄重新對應至其他位置，請將此參數設為「開啟」。 預設值為「off」。 </p> <p>範例： <span class="filepath"> ExpPartialMatch關閉</span> </p> <p> <p>注意：將此參數設為「on」時請務必小心。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> LogAllNewUsers </td> 
   <td colname="col2"> <p>確定是否記錄每個新用戶的首次點擊，即使用戶請求由ContentFilterExclude參數篩選掉的文檔類型。 </p> <p>預設值為「否」。 </p> <p>通常，影像檔案會由ContentFilterExclude參數篩選掉。 如果LogAllNewUsers設定為「是」，並且新用戶從伺服器獲取的第一個文檔就是映像，則該請求將被記錄。 如果LogAllNewUsers參數設為「no」或完全未設定（並假設影像已由ContentFilterExclude參數篩選掉），而新使用者從伺服器取得的第一個檔案就是影像，則該請求不會記錄。 </p> <p>範例： <span class="filepath"> LogAllNewUsers否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> MaxPageLoadTime </td> 
   <td colname="col2"> <p>發送器等待發送下一批資料包的秒數。 </p> <p>預設值為 15。 </p> <p>範例： <span class="filepath"> MaxPageLoadTime 15</span> </p> <p> <p>注意：請先聯絡Adobe諮詢服務，請勿變更此參數值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> PrivacyID </td> 
   <td colname="col2"> <p>可讓您停用訪客追蹤，以便用於遵循選擇退出原則。 </p> <p>啟用後， <span class="wintitle"> 感測器</span> 不會為任何將V1st Cookie設為指定PrivacyID的訪客記錄「封包」。 因為系統不會記錄這些訪客的資訊，因此不會將這些訪客的相關資訊傳送至 <span class="keyword"> data workbench伺服器</span> 來處理。 </p> <p>若要啟用此功能，您必須完成下列步驟： 
     <ol id="ol_5D658C5E4AB14F419029E0FFC52F1310"> 
      <li id="li_BF056439F92148169BF592731264C3CD"> PrivacyID的定義必須在 <span class="filepath"> txlogd.conf</span> 檔案 <span class="wintitle"> 感測器</span>. <p>範例： <span class="filepath"> PrivacyID 0</span> </p> </li> 
      <li id="li_3E20F068C2F94512A92F284C80273B1C">網站擁有者必須撰寫程式碼來設定訪客(V1st)Cookie，使Cookie ID值與定義的PrivacyID值相符：<span class="filepath"> txlogd.conf</span>." </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SiteTest </td> 
   <td colname="col2"> <p>傳送器(txlogd)定期傳送要求的位置，以查看網站是否正常運作。 </p> <p>請注意，位置是以下列格式指定，而非URL: </p> <p>http,<i>serverAddress,port,/resource</i> </p> <p>where <i>serverAddress</i> 是伺服器名稱或IP位址， <i>埠</i> 是伺服器的HTTP監聽埠， <i>資源</i> 是要要求的特定資源（可包含查詢字串）。 </p> <p>您可以指定多行SiteTest。 </p> <p>範例： <span class="filepath"> SiteTest http,localhost,80,/test.html</span> </p> <p> <p>注意：目前僅支援http。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TrackingCookie </td> 
   <td colname="col2"> <p>訪客瀏覽器上設定的Cookie名稱。 </p> <p>預設為「v1st」。 </p> <p>範例： <span class="filepath"> TrackingCookie v1st</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> VerifyCertName </td> 
   <td colname="col2"> <p>指示是否根據CertName參數驗證伺服器 </p> <p>預設值為「on」。 </p> <p>範例： <span class="filepath"> 驗證CertName</span> </p> </td> 
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
   <td colname="col1"> IISCaptureBytesSent </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時，才設定此參數。 </p> <p>告訴IIS <span class="wintitle"> 感測器</span> 應使用兩個可能的記錄「掛接」中的哪一個來記錄資料包 </p> <p>在IIS時使用此參數 <span class="wintitle"> 感測器</span> 未正確記錄資料包。 如果預設記錄掛接未正常運作，此參數會設為「關閉」。 預設值為「on」。 </p> <p>範例： <span class="filepath"> IISCaptureBytesSent on</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IISUseAlternateHandler </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時，才設定此參數。 </p> <p>告訴 <span class="wintitle"> 感測器</span> 兩個可能的「hook」中，哪一個應用來設定v1st cookie。 </p> <p>在IIS <span class="wintitle"> 感測器</span> 未正確設定v1st cookie。 如果預設連結未正確設定v1st Cookie，則此參數會設為「是」。 預設值為「否」。 </p> <p>範例： <span class="filepath"> IISUseAlternateHandler否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>依預設， <span class="wintitle"> 感測器</span> 在每個請求上傳送快取控制回應標題。 啟用快取控制功能時 <span class="wintitle"> 感測器</span> 發送一個Expires頭，其值為Thu, 1994年12月01日16:00:00 GMT至瀏覽器。 </p> <p>您可以視需要修改回應字串，方法是編輯 <span class="filepath"> txlogd.conf</span> 檔案： </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>範例: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl專用，max-age=0,must-revalidate</span> </p> <p>若要停用快取控制回應標頭的傳送，請為每行輸入連字型大小，如下所示： </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> </td> 
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
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時，才設定此參數。 </p> <p>告訴 <span class="wintitle"> 感測器</span> 兩個可能的「hook」中，哪一個應用來設定v1st cookie。 </p> <p>在Apache <span class="wintitle"> 感測器</span> 未正確設定v1st cookie。 如果預設連結未正確設定v1st Cookie，則此參數會設為「是」。 預設值為「否」。 </p> <p>範例： <span class="filepath"> ApacheUseAlternateHandler否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時，才設定此參數。 </p> <p>指示 <span class="wintitle"> 感測器</span> 嘗試在兩個鈎點中設定v1st cookie。 </p> <p>在Apache <span class="wintitle"> 感測器</span> 未正確設定v1st cookie。 預設值為「是」。 </p> <p>如果設為「是」，且未在第一個連結中正確設定v1st Cookie，則會使用第二個連結。 若設為「no」，您會設定ApacheUseAlternateHandler參數，以指出要使用哪個連結來設定v1st Cookie。 </p> <p>範例： <span class="filepath"> ApacheUseBothHandlers是</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>NewUserCacheControl </p> <p>CacheControl </p> </td> 
   <td colname="col2"> <p>依預設， <span class="wintitle"> 感測器</span> 在每個請求上傳送快取控制回應標題。 啟用快取控制功能時 <span class="wintitle"> 感測器</span> 發送一個Expires頭，其值為Thu, 1994年12月01日16:00:00 GMT至瀏覽器。 </p> <p>您可以視需要修改回應字串，方法是編輯 <span class="filepath"> txlogd.conf</span> 檔案： </p> <p> <span class="filepath"> NewUserCacheControl</span> <i>&lt;<span class="filepath"> string1</span>&gt;</i> </p> <p> <span class="filepath"> CacheControl</span> <i>&lt;<span class="filepath"> string2</span>&gt;</i> </p> <p>範例: </p> <p> <span class="filepath"> NewUserCacheControl no-cache=Set-Cookie</span> </p> <p> <span class="filepath"> CacheControl專用，max-age=0,must-revalidate</span> </p> <p>若要停用快取控制回應標頭的傳送，請為每行輸入連字型大小，如下所示： </p> <p> <span class="filepath"> NewUserCacheControl -</span> </p> <p> <span class="filepath"> CacheControl -</span> </p> <p> <p>注意：Adobe建議您不要停用此功能。 </p> </p> </td> 
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
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時，才設定此參數。 </p> <p>告訴 <span class="wintitle"> 感測器</span> 兩個可能的「hook」中，哪一個應用來設定v1st cookie。 </p> <p>在Apache <span class="wintitle"> 感測器</span> 未正確設定v1st cookie。 如果預設連結未正確設定v1st Cookie，則此參數會設為「是」。 預設值為「否」。 </p> <p>範例： <span class="filepath"> ApacheUseAlternateHandler否</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ApacheUseBothHandlers </td> 
   <td colname="col2"> <p>僅在使用Adobe諮詢服務時，才設定此參數。 </p> <p>指示 <span class="wintitle"> 感測器</span> 嘗試在兩個鈎點中設定v1st cookie。 </p> <p>在Apache <span class="wintitle"> 感測器</span> 未正確設定v1st cookie。 預設值為「是」。 </p> <p>如果設為「是」，且未在第一個連結中正確設定v1st Cookie，則會使用第二個連結。 若設為「no」，您會設定ApacheUseAlternateHandler參數，以指出要使用哪個連結來設定v1st Cookie。 </p> <p>範例： <span class="filepath"> ApacheUseBothHandlers是</span> </p> </td> 
  </tr> 
 </tbody> 
</table>
