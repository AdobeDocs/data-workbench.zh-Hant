---
description: 有關Report Server.cfg參數的資訊。
title: Report Server.cfg 參數
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1683'
ht-degree: 1%

---

# Report Server.cfg 參數{#report-server-cfg-parameters}

{{eol}}

有關Report Server.cfg參數的資訊。

範例 [!DNL Report Server.cfg] 顯示於 [設定與Insight Server的連線](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) 僅包含 [!DNL Report Server.cfg] 檔案。

如果您透過代理伺服器與Adobe授權伺服器連絡，則需要將授權向量及其參數新增至 [!DNL Report Server.cfg]. 以下是此向量及其參數的範例，您可將模型用於授權向量：

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

下表提供 [!DNL Report Server.cfg] 檔案參數：

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
   <td colname="col2"> <p>支援的Excel擴充功能包括： </p> <p>Excel擴充功能=字串： <span class="filepath"> .xlsx </span> </p> <p>Excel擴充功能=字串： <span class="filepath"> .xls </span> （此為預設值） </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 字型 </td> 
   <td colname="col2"> <p>選填。列出字型的向量 <span class="keyword"> 報表伺服器 </span> 應使用來轉譯以UTF8為基礎的Unicode特殊字元。 清單中的字型數量不限。 </p> <p>第一個字型應始終為Lucida Sans Console。 如果此參數未包含在 <span class="filepath"> Report Server.cfg </span> 檔案， <span class="keyword"> 報表伺服器 </span> 僅使用Lucida Sans控制台來顯示文本。 </p> <p> <span class="keyword"> 報表伺服器 </span> 使用清單中的第一個字型來呈現所有字元，直到遇到無法呈現的字元為止。 然後，它會使用清單中的第二個字型來轉譯該字元。 如果該字型不呈現字元， <span class="keyword"> 報表伺服器 </span> 使用清單中的第三個字型來呈現該字元等，直到它到達字型清單的結尾。 如果向量中未列出正確的字型， <span class="keyword"> 報表伺服器 </span> 顯示該字元的十進位值。 </p> <p> <p>注意：請勿變更此參數，同時 <span class="keyword"> 報表伺服器 </span> 執行中。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Gamma </span> 設定 <span class="filepath"> .png </span> 檔案輸出。 預設值為 1.6。 </p> <p> <p>注意：Adobe不建議變更此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 授權 </td> 
   <td colname="col2"> <p>選填。只有透過Proxy伺服器連絡Adobe的授權伺服器時，才需要修改此向量中的參數。 </p> <p>您設定為通過代理伺服器與Adobe的許可證伺服器聯繫的參數的節標識符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理地址 </td> 
   <td colname="col2"> 代理伺服器的地址 <span class="keyword"> 報表伺服器 </span> 必須使用來訪問Adobe的許可證伺服器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理密碼 </td> 
   <td colname="col2"> 選填。與 <span class="wintitle"> 代理用戶名 </span>. </td> 
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
   <td colname="col2"> 網路位置 <span class="keyword"> 報表伺服器 </span> 用於將伺服器的通用名稱解析為IP地址。 網路位置是在位於Data Workbench伺服器電腦之「位址」目錄的位址檔案中定義。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器 </td> 
   <td colname="col2"> <p>您要設定哪些Data Workbench伺服器電腦的參數區段識別碼 <span class="keyword"> 報表伺服器 </span> 必須連線才能產生報表。 這包括一個數字，表示此向量中列出了多少個項目。 </p> <p>對於每個伺服器，新增serverInfo項目，並視需要填入參數。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> Data Workbench伺服器電腦的IP位址，其 <span class="keyword"> 報表伺服器 </span> 必須連線才能產生報表。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 名稱 <span class="keyword"> 報表伺服器 </span> 在內部使用來識別data workbench伺服器。 這只是內部標籤，因此您可以使用任何您喜歡的名稱。 為保持一致，建議您使用伺服器數位憑證上所列的通用名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 埠 </td> 
   <td colname="col2"> 通過的埠 <span class="keyword"> 報表伺服器 </span> 與data workbench伺服器通訊。 對於安全連線，此值通常為443。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理地址 </td> 
   <td colname="col2"> 代理伺服器的地址 <span class="keyword"> 報表伺服器 </span> 必須使用來存取data workbench伺服器。 只有當需要代理伺服器才能連接到伺服器電腦時，才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理密碼 </td> 
   <td colname="col2"> 代理伺服器的密碼。 只有在需要代理伺服器才能連線至您的Data Workbench伺服器電腦時，才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理埠 </td> 
   <td colname="col2"> 代理伺服器的埠。 預設值為 8080。只有在需要代理伺服器才能連線至您的Data Workbench伺服器電腦時，才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 代理用戶名 </td> 
   <td colname="col2"> 代理伺服器的用戶名。 只有在需要代理伺服器才能連線至您的Data Workbench伺服器電腦時，才需要此參數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL用戶端憑證 </td> 
   <td colname="col2"> 的SSL憑證檔案名稱 <span class="keyword"> 報表伺服器 </span> 機器。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL伺服器公用名稱 </td> 
   <td colname="col2"> <span class="wintitle"> 伺服器公用名 </span> 列於data workbench伺服器的數位憑證上。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用SSL </td> 
   <td colname="col2"> 指出SSL是否用於Data Workbench伺服器與 <span class="keyword"> 報表伺服器 </span>. 選項為true或false。 預設值為true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 結果記憶體限制(KB) </td> 
   <td colname="col2"> <p>您要提供給報告和警報的記憶體量(KB)。 預設值為 50000。 </p> <p>執行報表時， <span class="keyword"> 報表伺服器 </span> 首先檢查此值，然後檢查「最大切片大小」參數中的值。 例如，如果將此參數設定為50,000，並將「最大切片大小」(Maximum Slice Size)設定為50, <span class="keyword"> 報表伺服器 </span> 一次只運行50個工作區，即使空間可用於運行更多工作區。 </p> <p> <p>注意：此限制不應超過Data Workbench伺服器的「查詢記憶體限制」參數中設定的值，且最理想的情況是，應設定得略低於 <span class="wintitle"> 查詢記憶體限制 </span> 為同時執行報表的其他使用者提供一些餘地。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最大切片大小 </td> 
   <td colname="col2"> 報表工作區的最大數量 <span class="keyword"> 報表伺服器 </span> 可同時執行。 預設值為 50。如需如何 <span class="keyword"> 報表伺服器 </span> 使用此設定，請參閱 <span class="wintitle"> 結果記憶體限制(KB) </span> 參數說明。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新軟體 </td> 
   <td colname="col2"> <p>指出是否允許此 <span class="keyword"> 報表伺服器 </span> 由data workbench伺服器更新的軟體。 選項為true或false。 預設值為true。 </p> <p>以下是可使用模型的此參數的示例： </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用OpenGL硬體呈現 </td> 
   <td colname="col2"> <p>控制 <span class="keyword"> 報表伺服器 </span> 使用硬體渲染（如電腦的圖形卡）生成報告輸出。 選項為true或false。 預設值為true。 </p> <p>只有在圖形卡出現問題時，此參數才應設定為false。 設為false時， <span class="keyword"> 報表伺服器 </span> 不會嘗試使用硬體呈現，並預設使用軟體呈現。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 報表 </td> 
   <td colname="col2"> 您用來設定報表之參數的區段識別碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 完成消息間隔 </td> 
   <td colname="col2"> <p>其頻率（以秒為單位） <span class="keyword"> 報表伺服器 </span> 在報告或警報生成期間運行查詢時打印完成狀態消息。 預設值為120秒。 </p> <p>範例：工作區查詢已完成62.145672%。 </p> <p>完成消息將寫入 <span class="filepath"> reportserver.log </span> 和會同步至伺服器。 此設定會控制 <span class="filepath"> status.txt </span> 會針對每個報表集來回傳送的檔案，以便以縮圖顯示完成百分比。 訊息會在報表集完成或到達間隔時（以先到者為準）傳送。 將此值設定得較高，不會影響縮圖在用戶端介面中產生報表的顯示率，但會影響您看到的臨時訊息數。 指定低值可能會導致系統花費大量時間來同步資料，因為資料是從 <span class="keyword"> 報表伺服器 </span> 每次 <span class="filepath"> status.txt </span> 訊息變更。 </p> <p>系統一律會傳送 <span class="filepath"> status.txt </span> 檔案，無論此設定參數的設定為何。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 設定檔 </td> 
   <td colname="col2"> <p>表示此向量中列出的項目數。 針對要建立報表的每個設定檔，新增 <span class="wintitle"> ReportProfile </span> 填入設定檔向量，並填入伺服器和設定檔參數。 </p> <p> <span class="wintitle"> 伺服器 </span> - <span class="keyword"> 報表伺服器 </span> 在內部使用來識別data workbench伺服器。 此名稱必須是Data Workbench伺服器的SSL憑證上所列的伺服器通用名稱。 </p> <p> <span class="wintitle"> 設定檔 </span>  — 要為其建立報表的設定檔名稱。 此名稱必須符合Data Workbench伺服器電腦上已命名的設定檔。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤的SMTP伺服器 </td> 
   <td colname="col2"> <p>要從中發送的SMTP伺服器的地址 <span class="wintitle"> 報表伺服器 </span> 錯誤。 </p> <p>範例： <span class="filepath"> mail.mycompany.com </span> </p> <p>使用上述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤密碼的SMTP伺服器 </td> 
   <td colname="col2"> <p>用於登錄到SMTP伺服器的密碼。 除非需要登入才能傳送郵件，否則此參數為選用。 </p> <p>使用上述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP伺服器，用於發送錯誤 </td> 
   <td colname="col2"> 您要傳送的電子郵件地址 <span class="wintitle"> 報表伺服器 </span> 錯誤。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤發送到的SMTP伺服器 </td> 
   <td colname="col2"> <p>傳送警報的電子郵件地址。 </p> <p>範例： <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>使用上述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤用戶名的SMTP伺服器 </td> 
   <td colname="col2"> <p>用於登錄到SMTP伺服器的用戶名。 除非需要登入才能傳送郵件，否則此參數為選用。 </p> <p>使用上述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 狀態間隔 </td> 
   <td colname="col2"> <p>其頻率（以秒為單位） <span class="wintitle"> 報表伺服器 </span> 產生狀態資訊並傳送至data workbench伺服器，以便顯示於 <span class="wintitle"> 詳細狀態 </span>. </p> <p>預設值為120秒。 不建議將此值設為小值（例如2分鐘），因為報表佇列可能需要數小時的時間才能執行。 在此情況下，您可以考慮將600秒到1200秒的設定。 </p> <p>如需 <span class="wintitle"> 詳細狀態 </span>，請參閱 <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight使用手冊 </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 更新間隔 </td> 
   <td colname="col2"> <p>與 <span class="keyword"> 報表伺服器 </span> 監視「設定檔」向量中列出的所有設定檔，以取得新報表和警報。 預設值為10分鐘。 </p> <p>您指定的時間會分到列出的所有設定檔中。 例如，如果您的間隔設為10分鐘，而您正在監控兩個設定檔，則每個設定檔會監控5分鐘。 如果在將新的或修改的報表或警報保存到配置檔案時正在監視配置檔案，則報告或警報將立即可用於生成。 </p> <p>若 <span class="wintitle"> 更新間隔 </span> 已設定為監視多個設定檔，請務必確保此設定足夠高，以便在設定的時間內載入所有設定檔。 在配置了許多大型維的系統中，例如，如果需要幾分鐘時間才能檢索到包含所有元素名稱的初始資料連接，則此設定必須足夠長，才能進行完全同步。 否則，系統會發出配置檔案同步錯誤。 </p> </td> 
  </tr> 
 </tbody> 
</table>
