---
description: 「參考頁面標籤執行呼叫」會插入至您要收集測量資料的網頁中。
title: 新增參考頁面標記執行呼叫
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# 新增參考頁面標記執行呼叫{#adding-reference-page-tag-execution-calls}

{{eol}}

「參考頁面標籤執行呼叫」會插入至您要收集測量資料的網頁中。

它應包含在HTML檔案的正文中，並可放置在全域包含頁尾（若適用）。 此 [!DNL Reference Page Tag Execution Call] 可由您的團隊修改，以收集在要求收集與Adobe諮詢服務團隊會議期間可能識別的其他資訊。

透過使用 [!DNL Reference Page Tag]，請完成下列步驟：

1. 將下列程式碼複製到您的HTML檔案內文：

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

1. 修改指向 [!DNL zig.js] 和 [!DNL zag.gif] 檔案。 例如：

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

請確保已在您的Web伺服器上設定適當的HTTP快取控制標題，以確保 [!DNL zig.js]和 [!DNL zag.gif] 瀏覽器不會快取檔案。 您可以使用下列兩種方法之一來設定HTTP快取控制標題資訊。 第一種方法是透過Web伺服器設定HTTP標題。 第二個方法是使用指令碼為每個特定頁面或內嵌物件設定HTTP標題。 使用指令碼方法，必須使用JSP或ASP等寫程式語言建立網頁。 然後對頁面進行指令碼，以便其發送適當的標頭資訊。 這種方法有兩個明顯的缺點：1)必須對所有頁面進行編碼，以傳送標題，2)頁面不能是靜態HTML，這對網站伺服器的效能有一定影響。

在Microsoft IIS上執行的網站可以透過Microsoft管理控制台新增適當的HTTP標題。 由Netscape iPlanet Web Server提供的網站可以編輯 [!DNL obj.conf] 檔案。 Apache Web Server使網站管理員能夠使用隨附的mod_headers模組自定義HTTP標頭，其中AOLServer可通過使用Tcl模組進行自定義。 在實作HTTP快取控制標題之前，請參閱您的Web伺服器平台專屬檔案。

一般而言，HTTP標題的結構應如下：

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
