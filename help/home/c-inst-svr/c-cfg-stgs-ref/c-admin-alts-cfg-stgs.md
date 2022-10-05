---
description: 為Insight Server、中繼器或轉換設定管理警報的指示。
title: 管理警報組態設定
uuid: c2be2d1e-d81d-4d9f-ac94-4b642dad90b9
exl-id: c75e442e-33e6-4fc8-8368-29482f09e1cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 4%

---

# 管理警報組態設定{#administrative-alerts-configuration-settings}

{{eol}}

為Insight Server、中繼器或轉換設定管理警報的指示。

在下列檔案中完成參數：

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
   <td colname="col2"> 類別的名稱。 需要預設類別。 請參閱此表中的錯誤類別。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤類別 </td> 
   <td colname="col2"> 可讓您將錯誤與錯誤分類檔案一起分類。 每個錯誤類別都可以有其自己的收件者集合和自己的節流延遲。 例如，您可以建立「關鍵」類別，限制延遲為0，這樣每個關鍵錯誤都會立即通過電子郵件發送給「收件者」清單中指定的收件者。 與錯誤分類檔案中的子字串不匹配的錯誤將分配給預設類別。 若要新增類別，請以滑鼠右鍵按一下數字，然後按一下 <span class="uicontrol"> 新增 </span> &gt; <span class="uicontrol"> 錯誤類別 </span>. 您也可以使用滑鼠右鍵動作來複製或移除它們。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 錯誤分類檔案 </td> 
   <td colname="col2"> <p>要用於對每個警報進行分類的檔案的名稱。 使用記事本建立此檔案。 此檔案的每行應有三欄，並以索引標籤分隔。 第一欄是錯誤中相符的字串。 ^符號與開頭相符，而$與字串結尾相符；其他所有字元都是字面匹配的。 第二欄是符合的錯誤類別，位於錯誤類別中。 第三則是替代訊息，會在所傳送電子郵件中的實際錯誤訊息前面加上。 如果未指定檔案，則所有錯誤均分類為預設值。 </p> <p>若要查看此檔案的範例，請參閱 <span class="filepath"> 錯誤類別.txt </span> 檔案。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 從 </td> 
   <td colname="col2"> <p>顯示在電子郵件「寄件者」參數中的地址。 </p> <p>範例： <span class="filepath"> server_errors@mycompany.com </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 最小磁碟空間(MB) </td> 
   <td colname="col2"> 當伺服器使用的任何目錄中的可用磁碟儲存低於此值時，伺服器會產生電子郵件警報。 預設值為 1000。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 感測器警報超時（分鐘） </td> 
   <td colname="col2"> <p>當伺服器未收到來自已配置和先前連接的資料時，它會生成電子郵件警報 <span class="wintitle"> 感測器 </span> 在這個時間範圍內。 預設值為 15。 </p> <p> <p>注意：  <span class="wintitle"> 感測器 </span> 警報逾時僅適用於 <span class="wintitle"> 感測器 </span> 已刪除。 如果伺服器的服務停止並重新啟動，且 <span class="wintitle"> 感測器 </span> 不連接，伺服器不生成電子郵件警報。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器位址 </td> 
   <td colname="col2"> <p>傳出電子郵件的SMTP伺服器地址。 </p> <p>範例： <span class="filepath"> mail.mycompany.com </span></p> <p>使用上述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器密碼 </td> 
   <td colname="col2"> <p>用於登錄到SMTP伺服器的密碼。 除非需要登入才能傳送郵件，否則此參數為選用。 </p> <p>使用上述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 伺服器用戶 </td> 
   <td colname="col2"> <p>用於登錄到SMTP伺服器的用戶ID/名稱。 除非需要登入才能傳送郵件，否則此參數為選用。 </p> <p>使用上述功能需要SMTP伺服器。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 節流延遲（秒） </td> 
   <td colname="col2"> 該類別中兩個錯誤之間需經過的最小秒數，才能傳送電子郵件。 值0會立即傳送電子郵件。 </td> 
  </tr> 
 </tbody> 
</table>
