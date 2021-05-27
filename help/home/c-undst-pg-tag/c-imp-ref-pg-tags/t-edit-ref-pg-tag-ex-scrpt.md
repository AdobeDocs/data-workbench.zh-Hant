---
description: 「參考頁面標籤」由駐留在Web伺服器上的「頁面標籤執行指令碼」組成，在呼叫時，會為網站訪客請求的頁面收集所有用戶端資料。
title: 編輯參考頁面標記執行指令碼
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# 編輯參考頁面標記執行指令碼{#editing-the-reference-page-tag-execution-script}

「參考頁面標籤」由駐留在Web伺服器上的「頁面標籤執行指令碼」組成，在呼叫時，會為網站訪客請求的頁面收集所有用戶端資料。

您可以修改[!DNL Reference Page Tag Execution Script]以收集在與Adobe諮詢服務團隊進行需求收集會議期間可識別的其他資訊。 [!DNL Reference Page Tag Execution Script]相對較小，可避免網頁上大量新增下載內容。

在名為[!DNL zig.js]的檔案中向您提供以下[!DNL Reference Page Tag Execution Script]代碼：

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

若要透過使用[!DNL Reference Page Tag]來加速資料收集，請完成下列步驟：

1. 將名為[!DNL zag.gif]的1像素影像檔案建立或放置到Web伺服器上的目錄。
1. 修改cd變數以參考參考[!DNL zag.gif]檔案所參考的網站或Adobe托管服務網域的適當網域。 對檔案的引用是通過執行[!DNL zig.js]檔案函式建立的。 例如：

   ```
   //www.mysite.com
   ```

1. 修改cu變數以參考[!DNL zag.gif]檔案位置的適當路徑。 例如

   ```
   /scripts
   ```

1. 確保為[!DNL zag.gif]和[!DNL zig.js]檔案建立適當的快取控制標頭。
