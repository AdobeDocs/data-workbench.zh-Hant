---
description: 「參考頁面標籤」由駐留在Web伺服器上的「頁面標籤執行指令碼」組成，在呼叫時，會為網站訪客請求的頁面收集所有用戶端資料。
title: 編輯參考頁面標記執行指令碼
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 7%

---

# 編輯參考頁面標記執行指令碼{#editing-the-reference-page-tag-execution-script}

{{eol}}

「參考頁面標籤」由駐留在Web伺服器上的「頁面標籤執行指令碼」組成，在呼叫時，會為網站訪客請求的頁面收集所有用戶端資料。

您可以修改 [!DNL Reference Page Tag Execution Script] 收集在與Adobe諮詢服務團隊進行的需求收集會議中可識別的其他資訊。 此 [!DNL Reference Page Tag Execution Script] 大小相對較小，可避免網頁中大量新增下載項目。

以下 [!DNL Reference Page Tag Execution Script] 程式碼會以名為 [!DNL zig.js]:

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

透過使用 [!DNL Reference Page Tag]，請完成下列步驟：

1. 建立或放置1個像素的影像檔案，命名為 [!DNL zag.gif] 進入網路伺服器上的目錄。
1. 修改cd變數，以參考您的網站或Adobe管理服務網域的適當網域，從中 [!DNL zag.gif] 檔案時，才會考量此變數。 對檔案的參考會透過 [!DNL zig.js] 檔案函式。 例如：

   ```
   //www.mysite.com
   ```

1. 修改cu變數以參考指向 [!DNL zag.gif] 檔案。 例如

   ```
   /scripts
   ```

1. 確保為 [!DNL zag.gif] 和 [!DNL zig.js] 檔案。
