---
description: 設定Insight Server、Repeater或Transform管理警報的指示。
title: 管理警報組態設定
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# 管理警報組態設定{#administrative-alerts-configuration-settings}

設定Insight Server、Repeater或Transform管理警報的指示。

完成下列檔案中的參數：

[!DNL Product Name installation directory\Components\Administrative Alerts.cfg]

<table id="table_5A2298906D5F4215B8FAC42CACBC0002"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 類別 </td> 
   <td colname="col2"> 類別的名稱。 需要「預設」類別。 請參閱此表中的錯誤類別。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤類別 </td> 
   <td colname="col2"> 可讓您將錯誤與錯誤分類檔案一起分類。 每個「錯誤類別」可以有自己的「收件者」集和自己的「限制延遲」。 例如，您可以建立「嚴重」類別，限制延遲為0，如此每個重大錯誤都會立即以電子郵件傳送給「收件者」清單中指定的收件者。 與錯誤分類檔案中的子字串不匹配的錯誤將分配給預設類別。 要添加新類別，請按一下右鍵某個數字，然後按一下「Add New </span> &gt; <span class="uicontrol"> Error Category </span>（添加新<span class="uicontrol"> &gt; 錯誤類別）」。 您也可以使用滑鼠右鍵動作來複製或移除它們。 </span></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤分類檔案 </td> 
   <td colname="col2"> <p>要用來分類每個警報的檔案名。 使用記事本建立此檔案。 此檔案每行應有三欄，以標籤分隔。 第一欄是要在錯誤中比對的字串。 ^符號與開頭匹配，$與字串結尾匹配；其他所有字元都是字面匹配的。 第二欄是相符錯誤的類別，位於錯誤類別中。 第三條是替代訊息，會在傳送的電子郵件中附加於實際錯誤訊息。 如果未指定任何檔案，所有錯誤都會歸類為「預設」。 </p> <p>要查看此檔案的示例，請參見Lookups目錄中的<span class="filepath"> Error Categories.txt </span>檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 從 </td> 
   <td colname="col2"> <p>出現在電子郵件訊息「from」參數中的地址。 </p> <p>範例：<span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小磁碟空間(MB) </td> 
   <td colname="col2"> 當伺服器使用的任何目錄中的可用磁碟儲存降到低於此值時，伺服器會生成電子郵件警報。 預設值為 1000。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器警報超時（分鐘） </td> 
   <td colname="col2"> <p>當伺服器未從已配置且先前連接的<span class="wintitle">感測器</span>中收到資料時，該伺服器會生成電子郵件警報。 預設值為 15。 </p> <p> <p>注意： <span class="wintitle">感測器</span>警報超時僅在<span class="wintitle">感測器</span>的現有連接中斷時工作。 如果伺服器的服務停止並重新啟動，而<span class="wintitle">感測器</span>未連接，則伺服器不會生成電子郵件警報。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器位址 </td> 
   <td colname="col2"> <p>傳出電子郵件的SMTP伺服器地址。 </p> <p>範例：<span class="filepath"> mail.mycompany.com </span></p> <p>使用所述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器密碼 </td> 
   <td colname="col2"> <p>登錄到SMTP伺服器的口令。 除非需要登入才能傳送郵件，否則此參數為可選參數。 </p> <p>使用所述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器使用者 </td> 
   <td colname="col2"> <p>登錄到SMTP伺服器的用戶ID/名稱。 除非需要登入才能傳送郵件，否則此參數為可選參數。 </p> <p>使用所述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 限制延遲（秒） </td> 
   <td colname="col2"> 要傳送電子郵件的此類別中兩個錯誤之間必須經過的最小秒數。 值0會立即傳送電子郵件。 </td> 
  </tr> 
 </tbody> 
</table>
