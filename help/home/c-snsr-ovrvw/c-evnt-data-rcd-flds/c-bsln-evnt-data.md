---
description: 有關Sensor記錄的基線事件資料記錄欄位的資訊。
title: 基線事件資料記錄欄位
uuid: aa36d332-089c-4ae2-98e2-a93d2fa023b7
exl-id: ad3d8806-863a-4871-a35b-6680163f00ac
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 3%

---

# 基線事件資料記錄欄位{#baseline-event-data-record-fields}

有關Sensor記錄的基線事件資料記錄欄位的資訊。

<table id="table_E29606BB010E4DB48C463979B7BEC769">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 欄位 </th>
   <th colname="col2" class="entry"> 說明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> c-ip </td>
   <td colname="col2"> <p>向伺服器發出的請求中包含的客戶端的IP地址。 </p> <p>例如: 207.68.146.68 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(cookie) </td>
   <td colname="col2"> <p>用戶端隨請求傳送的Cookie。 </p> <p>範例：v1st=42FDF66DE610CF36;ASPSESSIONIDQCATDAQC=GPIBKEIBFFIPLOJMKCAAEPM; </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(referrer) </td>
   <td colname="col2"> <p>由用戶端隨請求傳送至伺服器的HTTP反向連結字串。 </p> <p>範例：https://www.mysite.net/cgi-bin/websearch?qry </p> <p>如果您使用頁面標籤，cs(referrer)是包含標籤影像的檔案的完整URL，包括HTTP或HTTP。 </p> <p>此外，您還可以配置Apache（1.3、2.0和2.2）和IIS感測器來捕獲用於請求的埠，以便識別HTTP與HTTPS請求。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs(user-agent) </td>
   <td colname="col2"> <p>由客戶端發送的字串及其向伺服器的請求，該字串指示客戶端的用戶代理類型。 </p> <p>範例：Mozilla/5.0(Windows;U;Windows NT 5.1;美國；rv:1.7)Gecko/20040707 Firefox/0.9.2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-method </td>
   <td colname="col2"> <p>HTTP要求的方法類型 </p> <p>範例：GET </p> <p>參考資料：https://www.w3.org/TR/2000/NOTE-shoplogfileformat-20001115/#field_method </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-query </td>
   <td colname="col2"> <p>URI的查詢字串部分（stem +查詢字串= URI） </p> <p>前面有問號(?) 且可包含一或多個以&amp;符號分隔的名稱值組。 </p> <p>範例：page=homepage </p> </td>
  </tr>
  <tr>
   <td colname="col1"> cs-uri-stem </td>
   <td colname="col2"> <p>URI的幹部分（乾+查詢字串= URI） </p> <p>乾是伺服器上請求資源的實際路徑或邏輯路徑。 </p> <p>範例：/index.asp </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc(content-type) </td>
   <td colname="col2"> <p>由伺服器報告的客戶端請求的資源的內容類型。 </p> <p>範例：text/html, image/png, image/gif, video/mpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-bytes </td>
   <td colname="col2"> <p>響應請求從伺服器發送到客戶端的資料位元組數。 </p> <p>例如: 4996 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> sc-status </td>
   <td colname="col2"> <p>伺服器返回給客戶端的狀態代碼。 </p> <p>例如: 200 </p> <p>參考資料：https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html </p> </td>
  </tr>
  <tr>
   <td colname="col1"> s-dns </td>
   <td colname="col2"> <p>所請求資源的主機的完全限定的域名或IP地址。 </p> <p>範例：www.omniture.com </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x實驗 </td>
   <td colname="col2"> <p>請求時客戶端所屬的所有受控實驗名稱和組的清單。 </p> <p>範例：Home_Exp.Group_1,Registration_Exp.Group_2 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-timestamp </td>
   <td colname="col2"> <p>伺服器收到請求的日期和時間(GMT)。 </p> <p>時間以1600年1月1日以來的100納秒數表示。 </p> <p>範例：127710989320000000會是2005年9月13日星期二11:28:52.0000000的x-timestamp值。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> x-trackingid </td>
   <td colname="col2"> <p>由<span class="wintitle">感測器</span>設定、由客戶端向伺服器提供的、在永久Cookie中找到的唯一瀏覽器標識符的64位十六進位值。 </p> <p>範例：42FDF66DE610CF36 </p> </td>
  </tr>
 </tbody>
</table>

[!DNL data workbench server]可從基線事件資料記錄欄位衍生許多變數。 如需詳細資訊，請參閱&#x200B;*資料集組態指南*。
