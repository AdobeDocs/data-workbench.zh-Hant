---
description: 設定Insight Server或中繼器通訊的指示。
title: 通訊組態設定
uuid: 03297cf0-eb55-4db0-b692-eba24fcf947c
exl-id: a35788d1-de36-4350-a107-eee392e44503
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 5%

---

# 通訊組態設定{#communications-configuration-settings}

設定Insight Server或中繼器通訊的指示。

完成下列檔案中的參數：

[!DNL Product Name installation directory\Components\Communications.cfg]

>[!NOTE]
>
>在修改本表中未列出的任何參數之前，請與Adobe聯繫。

<table id="table_C87F1150E53548F484A8C0CFE91F1079"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 訪問控制檔案 </td> 
   <td colname="col2"> <p><span class="filepath"> Access Control.cfg </span>檔案的位置。 預設位置是<span class="keyword"> Insight Server </span>或<span class="wintitle"> Repeater </span>安裝目錄內的<span class="filepath"> Access Control </span>資料夾。 </p> <p>範例：<code>Access Control File = Path: Access Control\\Access Control.cfg</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問日誌目錄 </td> 
   <td colname="col2"> <p>要將審計日誌映射到的資料夾。 </p> <p>範例：<code>Access Log Directory = string: Audit\\</code> </p> <p> <p>注意： 您可以將審計日誌映射到另一個本地驅動器(例如：<span class="filepath">字串：P:\\Audit\\ </span>)，但不將審計日誌映射到網路驅動器。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 訪問日誌詳細 </td> 
   <td colname="col2"> 此參數可設為true或false。 它用於啟用和禁用審計日誌篩選。 若要確保記錄每個請求，請將參數設為True。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP介面 </td> 
   <td colname="col2"> <p>當兩個網卡可用於訪問兩個不同網路時使用的IP地址。 </p> <p>範例：<code>IP Interface = string: &lt; IP Address &gt;</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 連接埠 </td> 
   <td colname="col2"> <p><span class="keyword"> Insight Server </span>或<span class="wintitle"> Repeater </span>監聽的非安全(HTTP)埠。 預設連接埠為 80。輸入值0會禁用非安全連接。 </p> <p>範例：<code>Port = int: 80</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL密碼 </td> 
   <td colname="col2"> 有些環境需要比其他環境更強的通訊安全性。 如果您想使用特定的SSL密碼套件，可以使用此參數來指定它。 <p>範例：<code>SSL Ciphers = string: AES256-SHA256</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL埠 </td> 
   <td colname="col2"> <p><span class="keyword"> Insight Server </span>或<span class="wintitle"> Repeater </span>監聽的安全（透過SSL）埠。 預設連接埠為 443。輸入值0將禁用安全連接。 </p> <p>範例：<span class="filepath"></span> </p> <code>SSL Port = int: 443</code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>LoggingServer: </td> 
   <td colname="col2"> 記錄伺服器設定的標題。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 客戶名稱 </td> 
   <td colname="col2"> <p>管理警報中「未指定」客戶的客戶名稱，如下例所示： </p> <p>"15中沒有從感測器XYZ接收客戶「未指定」的資料。" </p> <p>範例：<code> 1&nbsp;=&nbsp;LoggingServer:&nbsp; 
      &nbsp;&nbsp;Customer&nbsp;Name&nbsp;=&nbsp;string:&nbsp;CompanyAB </code> </p> <p>使用上述範例，「未指定」客戶的管理警報現在會如下所示： </p> <p>「15年內沒有從感測器XYZ為客戶『CompanyAB』收到資料。」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> 本機路徑=字串：記錄\\ </p> </td> 
   <td colname="col2"> <p>要儲存日誌檔案的資料夾。 </p> <p>範例： </p> <code> 9&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Logs\\ </code> <p>要能夠從<span class="wintitle">伺服器檔案管理器</span>訪問此資料夾，此參數中指定的位置必須與<span class="filepath">日誌處理。cfg </span>檔案中「日誌路徑」參數中指定的位置相匹配。 有關在<span class="filepath"> Log Processing.cfg </span>檔案中修改Logs目錄的詳細資訊，請參閱<i>資料集配置指南</i>中的Log Processing Configuration File一章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>FileServer: </p> <p> 本機路徑=字串：審核\\ </p> </td> 
   <td colname="col2"> <p>要將審計日誌映射到的資料夾。 </p> <p>範例： </p> <code> 5&nbsp;=&nbsp;FileServer:&nbsp; 
     &nbsp;&nbsp;Local&nbsp;Path&nbsp;=&nbsp;string:&nbsp;Audit\\ </code> <p>注意:  <p>您可以將審計日誌映射到另一個本地驅動器(例如：<span class="filepath">字串：P:\\Audit\\ </span>)，但不將審計日誌映射到網路驅動器。 </p> <p>要能夠從<span class="wintitle">伺服器檔案管理器</span>訪問此資料夾，此參數中指定的位置必須與此檔案中「訪問日誌目錄」參數中的位置匹配。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>n=</i>NormalizeServer: </td> 
   <td colname="col2"> <p>此參數僅適用於<span class="keyword"> Insight Server </span>。 </p> <p>有關為<span class="keyword"> Insight Server </span>群集指定集中式標準化伺服器的詳細資訊，請參閱<i>資料集配置指南</i>中的「日誌處理配置檔案」一章。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <i>n=</i>ReportStatusServer: </p> <p> URI =字串：/ReportStatus.vsp </p> </td> 
   <td colname="col2"> <p>此參數僅適用於<span class="keyword"> Insight Server </span>。 </p> <p>可讓您在<span class="keyword"> Insight Server </span>的「詳細狀態」介面中檢視<span class="keyword">報表的</span>狀態。 </p> </td> 
  </tr> 
 </tbody> 
</table>
