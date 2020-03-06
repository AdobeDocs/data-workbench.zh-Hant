---
description: 參考頁面標籤執行呼叫會插入您要收集測量資料的網頁。
solution: Analytics
title: 新增參考頁面標籤執行呼叫
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 新增參考頁面標籤執行呼叫{#adding-reference-page-tag-execution-calls}

參考頁面標籤執行呼叫會插入您要收集測量資料的網頁。

它應包含在HTML檔案的正文中，並可放置在全域包含頁尾（如果適用）中。 您的 [!DNL Reference Page Tag Execution Call] 團隊可修改此項資訊，以收集在與Adobe諮詢服務團隊進行需求收集會議時可能識別的其他資訊。

若要透過使用來協助資料收集， [!DNL Reference Page Tag]請完成下列步驟：

1. 將下列程式碼複製到HTML檔案內文：

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. 修改指向和檔案位置的 [!DNL zig.js] 路 [!DNL zag.gif] 徑。 例如：

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

請確定您的Web伺服器上已設定適當的HTTP快取控制標題，以確保瀏 [!DNL zig.js]覽 [!DNL zag.gif] 器未快取和檔案。 您可以使用兩種方法之一來設定HTTP快取控制標題資訊。 第一種方法是透過Web伺服器設定HTTP標頭。 第二種方法是使用指令碼為每個特定頁面或內嵌物件設定HTTP標題。 使用指令碼方法，網頁必須使用JSP或ASP等程式設計語言來建立。 然後會編寫頁面的指令碼，以便傳送適當的頁首資訊。 這種方法有兩個明顯的缺點：1)所有頁面都必須編碼以傳送標題，2)頁面不能是靜態HTML，這對Web伺服器效能有一定影響。

在Microsoft IIS上執行的網站可以透過Microsoft管理控制台新增適當的HTTP標題。 從Netscape iPlanet Web Servers提供的網站可編輯網站組態目錄 [!DNL obj.conf] 內的檔案，以達成此目的。 Apache Web Server可讓網站管理員使用隨附的mod_headers模組自訂HTTP標頭，AOLServer可透過使用Tcl模組進行自訂。 在實作HTTP快取控制標題之前，您應參閱網頁伺服器平台專屬的檔案。

一般而言，HTTP標題的結構應如下：

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

