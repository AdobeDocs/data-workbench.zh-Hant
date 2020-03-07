---
description: 「參考頁面標籤」由駐留在網站伺服器上的「頁面標籤執行指令碼」組成，而呼叫時，會針對網站訪客要求的頁面收集所有用戶端資料。
solution: Analytics
title: 編輯參考頁標籤執行指令碼
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 編輯參考頁標籤執行指令碼{#editing-the-reference-page-tag-execution-script}

「參考頁面標籤」由駐留在網站伺服器上的「頁面標籤執行指令碼」組成，而呼叫時，會針對網站訪客要求的頁面收集所有用戶端資料。

您可以修改以收 [!DNL Reference Page Tag Execution Script] 集其他資訊，這些資訊可能會在要求收集與Adobe諮詢服務團隊的會議期間識別。 它的 [!DNL Reference Page Tag Execution Script] 大小相對較小，可避免在您的網頁上增加大量下載內容。

以下程 [!DNL Reference Page Tag Execution Script] 式碼會在名為的檔案中提供給您 [!DNL zig.js]:

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

若要透過使用來協助資料收集， [!DNL Reference Page Tag]請完成下列步驟：

1. 建立或置入名為1像素乘1像素的影像檔， [!DNL zag.gif] 並放入Web伺服器上的目錄。
1. 修改cd變數，以參考您網站的適當網域或參考檔案的Adobe受管 [!DNL zag.gif] 理服務網域。 通過執行檔案函式建立對檔案的 [!DNL zig.js] 引用。 例如：

   ```
   //www.mysite.com
   ```

1. 修改cu變數，以參考檔案位置的適當路 [!DNL zag.gif] 徑。 例如

   ```
   /scripts
   ```

1. 確保為和檔案建立適當的快取控 [!DNL zag.gif] 制標 [!DNL zig.js] 頭。
