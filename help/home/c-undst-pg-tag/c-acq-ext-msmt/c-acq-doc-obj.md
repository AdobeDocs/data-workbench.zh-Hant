---
description: 使用JavaScript檔案物件模型時，可使用其他指令碼方法來增加zig.js檔案的要求。
title: 取得文件物件
uuid: 7681c337-b147-4937-9d9c-0ff48d9bdd00
exl-id: eae6609c-be86-44cf-a1a1-69ffb43231fa
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# 取得文件物件{#acquiring-document-objects}

使用JavaScript檔案物件模型時，可使用其他指令碼方法來增加zig.js檔案的要求。

諸如META標籤的值、DIV標籤的ID值等資訊可由名稱參照，並收集為變數以用於分析。 例如，若要動態擷取HTML檔案的META元素內包含的資訊，您可以使用下列JavaScript語法：

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var m0 = document.getElementsByTagName('META')[0]; //define the first instance of META 
var metacontent = m0.getAttribute('content'); //get the ‘content’ value of META 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_1"] = metacontent; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1= | 與METAVALUE查詢字串變數關聯的值。 此值表示HTML文檔的META元素內的資料。 | v_1=此頁面提供與感謝訂購頁面相關的內容。 |

收集資料後，您可以設定Data Workbench伺服器以處理此測量資料，以便進行分析和製作報表。
