---
description: 您的報表入口網站的存取權和權限都可使用個別使用者和群組帳戶加以控制。
title: 編輯 Email.asp 檔案
uuid: 18251170-0317-4a32-b9e1-4ebf2d7ad123
exl-id: e984f12f-362a-4dee-9af3-6d7a38a178a4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 2%

---

# 編輯 Email.asp 檔案{#edit-the-email-asp-file}

您的報表入口網站的存取權和權限都可使用個別使用者和群組帳戶加以控制。

每次您新增帳戶或編輯現有帳戶時，都會傳送確認電子郵件至您為該帳戶指定的電子郵件地址（請參閱[使用帳戶](../../../home/c-rpt-oview/c-admin-rpt/c-work-accts/c-work-accts.md#concept-c933a1940bda4a3489d61d8af315e45d)），並複製至您在[!DNL email.asp]檔案中指定的電子郵件地址。

>[!NOTE]
>
>通知電子郵件只有在您為帳戶指定電子郵件地址並正確設定[!DNL email.asp]檔案時才會傳送給帳戶使用者。 如果您不想為帳戶傳送通知電子郵件，請將帳戶的電子郵件欄位留空。

此檔案位於`\*PortalName*\PortalASP`資料夾中。

1. 在運行IIS的電腦上，在文本編輯器（如記事本）中開啟[!DNL email.asp]檔案。
1. 設定下列變數：

<table id="table_44F52DA266364DF993C40678A28E0F0D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於此變數。.. </th> 
   <th colname="col2" class="entry"> 提供此資訊。.. </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> smtpserver </td> 
   <td colname="col2"> <p>發送消息的SMTP伺服器的DNS名稱或IP地址。 </p> <p>例如：<span class="filepath"> mail.hq.omniture.com</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpserverport </td> 
   <td colname="col2"> SMTP伺服器監聽連接的埠。 這通常是埠25。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sendusing </td> 
   <td colname="col2"> <p>指示消息的發送方式。 值包括： </p> <p>1 —— 使用本地安裝的SMTP服務發送消息。 如果SMTP服務安裝在運行指令碼的電腦上，請使用此值。 </p> <p>2 —— 使用網路上的SMTP服務發送消息。 如果運行指令碼的電腦上未安裝SMTP服務，請使用此值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> smtpconnectiontimeout </td> 
   <td colname="col2"><span class="wintitle"> Report</span>在連接超時之前應等待SMTP伺服器響應的時間。 </td> 
  </tr> 
 </tbody> 
</table>

1. 對於[!DNL NewUserEmail()]和[!DNL UpdateUserEmail()]函式，請設定以下變數：

   <table id="table_91C5E36B84A94C4097EE5993592BE587"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 對於此變數。.. </th> 
      <th colname="col2" class="entry"> 提供此資訊。.. </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 從 </td> 
      <td colname="col2">您要在確認電子郵件的「寄件者」標題行中顯示的文字。 此值可能與<span class="wintitle"> CC</span>值相同。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> CC </td> 
      <td colname="col2"> <p>選填。應接收與新用戶帳戶和已更改用戶帳戶有關的所有消息副本的人員或別名的有效電子郵件地址。 您可以使用逗號（無空格）來分隔地址，以指定多個電子郵件地址。 </p> <p>例如：<span class="filepath"> admin@company.com,joemanager@company.com</span></p> <p> <p>注意： 收件者會收到包含使用者密碼的電子郵件副本。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 主旨 </td> 
      <td colname="col2"> 您要在確認電子郵件的「主旨」標題行中顯示的文字。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> WebPath </td> 
      <td colname="col2"> <p>入口網站的實際路徑。 </p> <p>例如：<span class="filepath"> http://portal.omniture.com/Example</span></p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 內文 </td> 
      <td colname="col2"> <p>自動產生的電子郵件中包含的文字。 </p> <p>例如，以下是傳送電子郵件中的預設文字，以提供登入資訊： 
      <ul id="ul_7FF2E7399AB64D279EC5794AB02C9749">
      <li id="li_7CBCC5CFF9E04776BBC893278785AEE7">您的Web入口網站登入資訊如下： </li>
      <li id="li_5346F0AB3568444B88117C295D8E99C5"><p>用戶名：username </p><p>新密碼：密碼 </p></li>
      <li id="li_B0D1FAE818BA42CF8546796800A1AA08"><p>您可以使用下列URL存取入口網站： </p><p><span class="filepath"> http://WebPath</span></p></li>
      <li id="li_7CD71EBDFA1D418F960040569CD511EB">登入入口網站後，您可以在<span class="wintitle">管理員</span>標籤上變更密碼。 </li>
      </ul></p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 儲存並關閉檔案。
