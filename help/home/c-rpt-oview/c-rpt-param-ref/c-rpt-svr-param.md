---
description: Report Server.cfg參數的相關資訊。
title: Report Server.cfg 參數
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 2%

---

# Report Server.cfg 參數{#report-server-cfg-parameters}

Report Server.cfg參數的相關資訊。

[Configuring the Connection to Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)中顯示的範例[!DNL Report Server.cfg]僅包含[!DNL Report Server.cfg]檔案中預設包含的參數。

如果您透過代理伺服器與Adobe授權伺服器聯絡，則需要將授權向量及其參數新增至[!DNL Report Server.cfg]。 以下是此向量及其參數的範例，您可將模型用於您的授權向量：

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

下表說明[!DNL Report Server.cfg]檔案參數：

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Excel擴充功能 </td> 
   <td colname="col2"> <p>支援的Excel擴充功能包括： </p> <p>Excel Extension =字串：<span class="filepath"> .xlsx </span> </p> <p>Excel Extension =字串：<span class="filepath"> .xls </span>（此為預設值） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 字型 </td> 
   <td colname="col2"> <p>選填。列出<span class="keyword">報表伺服器</span>應用來轉譯UTF8-based Unicode特殊字元的字型的向量。 清單中的字型數目不受限制。 </p> <p>第一個字型應始終為Lucida Sans Console。 如果此參數未包含在<span class="filepath"> Report Server.cfg </span>檔案中，<span class="keyword"> Report Server </span>僅使用Lucida Sans控制台來顯示文字。 </p> <p> <span class="keyword"> 報表伺服 </span> 器使用清單中的第一個字型來轉換所有字元，直到遇到無法轉換的字元為止。然後，它會使用清單中的第二個字型來轉換該字元。 如果該字型未呈現字元，<span class="keyword">報表伺服器</span>會使用清單中的第三種字型來呈現該字元，依此類推，直到字元清單結尾為止。 如果向量中未列出正確的字型，<span class="keyword">報表伺服器</span>會顯示字元的十進位值。 </p> <p> <p>注意： 在<span class="keyword">報表伺服器</span>執行時，請勿變更此參數。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> 輸 </span> 出。png檔 <span class="filepath"> 案的Gamma </span> 設定。預設值為 1.6。 </p> <p> <p>注意： Adobe不建議變更此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 授權 </td> 
   <td colname="col2"> <p>選填。只有當您透過Proxy伺服器連絡Adobe的授權伺服器時，才需要修改此向量中的參數。 </p> <p>您設定透過Proxy伺服器連絡Adobe授權伺服器的參數區段識別碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理地址 </td> 
   <td colname="col2"> <span class="keyword">報告伺服器</span>必須用於訪問Adobe許可證伺服器的代理伺服器地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理密碼 </td> 
   <td colname="col2"> 選填。與<span class="wintitle">代理用戶名</span>關聯的口令。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理埠 </td> 
   <td colname="col2"> 代理伺服器的埠。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理用戶名 </td> 
   <td colname="col2"> 選填。用於訪問代理伺服器的用戶名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 網路位置 </td> 
   <td colname="col2"> <span class="keyword">報告伺服器</span>用於將伺服器的公用名稱解析為IP地址的網路位置。 網路位置定義在位於資料工作台伺服器電腦的「地址」目錄的地址檔案中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器 </td> 
   <td colname="col2"> <p>您設定的參數區段識別碼，以設定哪些資料工作台伺服器電腦<span class="keyword">報表伺服器</span>必須連線才能產生報表。 這包括一個數字，指出此向量中列出的項目數。 </p> <p>對於每台伺服器，添加serverInfo條目並根據需要完成參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <span class="keyword">報表伺服器</span>必須連線至的資料工作台伺服器電腦的IP位址，才能產生報表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> <span class="keyword">報表伺服器</span>在內部用來識別資料工作台伺服器的名稱。 這只是內部標籤，因此您可以使用任何您喜歡的名稱。 為保持一致性，建議您使用伺服器數字證書上列出的通用名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 連接埠 </td> 
   <td colname="col2"> <span class="keyword">報告伺服器</span>與資料工作台伺服器通信的埠。 對於安全連接，此值通常為443。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理地址 </td> 
   <td colname="col2"> <span class="keyword">報表伺服器</span>必須用來存取資料工作台伺服器的代理伺服器位址。 只有在需要代理伺服器才能連接到伺服器電腦時才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理密碼 </td> 
   <td colname="col2"> 代理伺服器的口令。 只有當需要代理伺服器才能連接到資料工作台伺服器電腦時，才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理埠 </td> 
   <td colname="col2"> 代理伺服器的埠。 預設值為 8080。只有當需要代理伺服器才能連接到資料工作台伺服器電腦時，才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理用戶名 </td> 
   <td colname="col2"> 代理伺服器的用戶名。 只有當需要代理伺服器才能連接到資料工作台伺服器電腦時，才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL用戶端憑證 </td> 
   <td colname="col2"> <span class="keyword">報表伺服器</span>機器的SSL憑證檔案名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL伺服器通用名稱 </td> 
   <td colname="col2"> <span class="wintitle"> 資料工作台 </span> 伺服器的數位憑證上列出的伺服器通用名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用SSL </td> 
   <td colname="col2"> 指出SSL是否用於在資料工作台伺服器與<span class="keyword">報表伺服器</span>之間進行安全通訊。 選項是true或false。 預設值為true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 結果記憶體限制(KB) </td> 
   <td colname="col2"> <p>您要提供給報告和警報的記憶體量（以KB為單位）。 預設值為 50000。 </p> <p>運行報告時，<span class="keyword">報告伺服器</span>首先檢查此值，然後檢查最大切片大小參數中的值。 例如，如果將此參數設為50,000，而「最大切片大小」為50，則<span class="keyword">報告伺服器</span>一次只運行50個工作區，即使有空間可運行更多工作區。 </p> <p> <p>注意： 此限制不應超過在資料工作台伺服器的「查詢記憶體限制」參數中設定的值，最理想的是，應設定為略低於<span class="wintitle">查詢記憶體限制</span>，以便為同時執行報表的其他使用者提供一些空間。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大切片大小 </td> 
   <td colname="col2"> <span class="keyword">報表伺服器</span>可同時執行的報表工作區數上限。 預設值為 50。有關<span class="keyword">報告伺服器</span>如何使用此設定的詳細資訊，請參見<span class="wintitle">結果記憶體限制(KB)</span>參數說明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新軟體 </td> 
   <td colname="col2"> <p>指示是否允許資料工作台伺服器更新此<span class="keyword">報告伺服器的</span>軟體。 選項是true或false。 預設值為true。 </p> <p>以下是可使用模型的此參數示例： </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用OpenGL硬體演算 </td> 
   <td colname="col2"> <p>控制<span class="keyword">報表伺服器</span>是否使用硬體演算（例如機器的圖形卡）來產生報表輸出。 選項是true或false。 預設值為true。 </p> <p>只有當您的圖形卡發生問題時，才應將此參數設為false。 當設為false時，<span class="keyword">報告伺服器</span>不會嘗試使用硬體渲染，並預設使用軟體渲染。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 報表 </td> 
   <td colname="col2"> 您設定報表之參數的區段識別碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完成消息間隔 </td> 
   <td colname="col2"> <p><span class="keyword">報告伺服器</span>在報告或警報生成期間運行查詢時打印完成狀態消息的頻率（以秒為單位）。 預設值為120秒。 </p> <p>範例：工作區查詢已完成62.145672%。 </p> <p>完成消息將寫入<span class="filepath"> reportserver.log </span>並與伺服器同步。 此設定會控制每個報表集之間來回傳送的<span class="filepath"> status.txt </span>檔案，讓縮圖顯示完成百分比。 當報表集完成或到達間隔時（以先到者為準），會傳送訊息。 設定此較高值不會影響您透過縮圖在用戶端介面中產生的報表顯示速率，但會影響您看到的臨時訊息數量。 指定低值可能會使系統花費大量時間同步資料，因為每次<span class="filepath"> status.txt </span>訊息變更時，資料會從<span class="keyword">報表伺服器</span>伺服器同步到描述檔、跨所有DPU以及所有連線的用戶端。 </p> <p>無論此配置參數的設定如何，系統都會在報告集完成時發送<span class="filepath"> status.txt </span>檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設定檔 </td> 
   <td colname="col2"> <p>數字，指出此向量中列出的項目數。 對於要為其建立報告的每個配置檔案，在「配置檔案」向量中添加<span class="wintitle"> ReportProfile </span>條目，並完成伺服器和配置檔案參數。 </p> <p> <span class="wintitle"> 伺服 </span> 器——報表伺服 <span class="keyword"> 器內部用 </span> 來識別資料工作台伺服器的名稱。此名稱必須是資料工作台伺服器的SSL憑證上所列的伺服器公用名稱。 </p> <p> <span class="wintitle"> Profile  </span> -要為其建立報告的配置檔案的名稱。此名稱必須與資料工作台伺服器電腦上的命名描述檔相符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤的SMTP伺服器 </td> 
   <td colname="col2"> <p>要通過電子郵件發送<span class="wintitle">報告伺服器</span>錯誤的SMTP伺服器地址。 </p> <p>範例：<span class="filepath"> mail.mycompany.com </span> </p> <p>使用所述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤口令的SMTP伺服器 </td> 
   <td colname="col2"> <p>登錄到SMTP伺服器的口令。 除非需要登入才能傳送郵件，否則此參數為可選參數。 </p> <p>使用所述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 發送錯誤的SMTP伺服器 </td> 
   <td colname="col2"> 您要傳送<span class="wintitle">報表伺服器</span>錯誤的電子郵件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 發送到的錯誤的SMTP伺服器 </td> 
   <td colname="col2"> <p>傳送警報的電子郵件地址。 </p> <p>範例：<span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>使用所述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤用戶名的SMTP伺服器 </td> 
   <td colname="col2"> <p>登錄到SMTP伺服器的用戶名。 除非需要登入才能傳送郵件，否則此參數為可選參數。 </p> <p>使用所述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 狀態間隔 </td> 
   <td colname="col2"> <p><span class="wintitle">報告伺服器</span>生成狀態資訊並將其發送到要顯示在<span class="wintitle">詳細狀態</span>中的資料工作台伺服器的頻率（以秒為單位）。 </p> <p>預設值為120秒。 不建議將此值設為小值（例如2分鐘），因為報告佇列可能需要數小時才能執行。 在這種情況下，您可以考慮設定600到1200秒。 </p> <p>如需<span class="wintitle">詳細狀態</span>的詳細資訊，請參閱<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight User Guide </a>的「Administrative Interfaces」一章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新間隔 </td> 
   <td colname="col2"> <p><span class="keyword">報表伺服器</span>監視「描述檔」向量中列出的所有描述檔，以取得新報表和警報的頻率（以分鐘為單位）。 預設值為10分鐘。 </p> <p>您指定的時間會分為所有列出的描述檔。 例如，如果您的間隔設定為10分鐘，而您正在監視兩個配置檔案，則每個配置檔案將被監視5分鐘。 如果在將新的或修改的報告或警報保存到配置檔案時監視配置檔案，則報告或警報可立即生成。 </p> <p>如果<span class="wintitle">更新間隔</span>配置為監視多個配置檔案，則此設定必須足夠高，以在配置的時間內載入所有配置檔案。 在配置了許多大維的系統中，例如，在需要幾分鐘時間檢索具有所有元素名稱的初始資料連接時，此設定必須足夠長，才能進行完全同步。 否則，系統會發出配置檔案同步錯誤。 </p> </td> 
  </tr> 
 </tbody> 
</table>
