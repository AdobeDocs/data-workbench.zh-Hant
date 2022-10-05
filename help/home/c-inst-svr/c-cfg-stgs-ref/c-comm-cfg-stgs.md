---
description: 設定Insight Server或中繼器通訊的指示。
title: 通訊組態設定
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# 通訊組態設定{#communications-configuration-settings}

{{eol}}

設定Insight Server或中繼器通訊的指示。

在下列檔案中完成參數：

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>修改此表中未列出的任何參數之前，請與Adobe聯繫。

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 存取控制檔案 </td> 
   <td colname="col2"> <p>位置 <span class="filepath"> Access Control.cfg </span> 檔案。 預設位置為 <span class="filepath"> 存取控制 </span> 資料夾 <span class="keyword"> Insight Server </span> 或 <span class="wintitle"> 中繼器 </span> 安裝目錄。 </p> <p>範例：<code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問日誌目錄 </td> 
   <td colname="col2"> <p>要將審核日誌映射到的資料夾。 </p> <p>範例：<code>Access Log Directory = string: Audit\\</code> </p> <p> <p>注意：您可以將審核日誌映射到另一個本地驅動器(例如： <span class="filepath"> 字串：P:\\Audit\\ </span>)，但不將審核日誌映射到網路驅動器。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問日誌詳細 </td> 
   <td colname="col2"> 此參數可設為true或false。 用於啟用和禁用審核日誌篩選。 若要確保記錄所有請求，請將參數設為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP介面 </td> 
   <td colname="col2"> <p>當兩個網卡可用於訪問兩個不同網路時使用的IP地址。 </p> <p>範例：<code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 埠 </td> 
   <td colname="col2"> <p>不安全(HTTP)埠， <span class="keyword"> Insight Server </span> 或 <span class="wintitle"> 中繼器 </span> 聽。 預設連接埠為 80。輸入0值將禁用不安全連接。 </p> <p>範例：<code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL加密 </td> 
   <td colname="col2"> 某些環境比其他環境要求更強的通訊安全性。 如果要使用特定的SSL密碼套件，可以使用此參數指定它。 <p>範例：<code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL埠 </td> 
   <td colname="col2"> <p>安全（透過SSL）連接埠， <span class="keyword"> Insight Server </span> 或 <span class="wintitle"> 中繼器 </span> 聽。 預設連接埠為 443。輸入0值將禁用安全連接。 </p> <p>範例：<span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> 記錄伺服器設定標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 客戶名稱 </td> 
   <td colname="col2"> <p>管理警報中「未指定」客戶的客戶名稱，如下列範例所示： </p> <p>"15中沒有從感測器XYZ收到客戶「未指定」的資料。" </p> <p>範例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>使用上述範例，「未指定」客戶的管理警報現在會顯示如下： </p> <p>「在15中沒有從感測器XYZ收到客戶『CompanyAB』的資料。」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>檔案伺服器： </p> <p> 本機路徑=字串：日誌\\ </p> </td> 
   <td colname="col2"> <p>要儲存日誌檔案的資料夾。 </p> <p>範例: </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>若要從 <span class="wintitle"> 伺服器檔案管理員 </span>，此參數中指定的位置必須符合您在 <span class="filepath"> Log Processing.cfg </span> 檔案。 如需有關修改 <span class="filepath"> Log Processing.cfg </span> ，請參閱 <i>資料集組態指南</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>檔案伺服器： </p> <p> 本機路徑=字串：審核\\ </p> </td> 
   <td colname="col2"> <p>要將審核日誌映射到的資料夾。 </p> <p>範例: </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注意：  <p>您可以將審核日誌映射到另一個本地驅動器(例如： <span class="filepath"> 字串：P:\\Audit\\ </span>)，但不將審核日誌映射到網路驅動器。 </p> <p>若要從 <span class="wintitle"> 伺服器檔案管理員 </span>，則此參數中指定的位置必須與您在此檔案的「訪問日誌目錄」參數中的位置匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>標準化伺服器： </td> 
   <td colname="col2"> <p>此參數僅適用於 <span class="keyword"> Insight Server </span>. </p> <p>有關為 <span class="keyword"> Insight Server </span> 叢集，請參閱 <i>資料集組態指南</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI =字串：/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>此參數僅適用於 <span class="keyword"> Insight Server </span>. </p> <p>可讓您檢視 <span class="keyword"> 報表 </span> 詳細狀態介面中 <span class="keyword"> Insight Server </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>
