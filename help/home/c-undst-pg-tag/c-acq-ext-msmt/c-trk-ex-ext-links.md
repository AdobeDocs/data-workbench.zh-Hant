---
description: 擷取第三方網站連結上的活動，以啟用「退出目標」分析。
solution: Analytics
title: 追蹤退出外部連結
topic: Data workbench
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 追蹤退出外部連結{#tracking-exits-to-external-links}

擷取第三方網站連結上的活動，以啟用「退出目標」分析。

網頁可包含第三方網站的連結，而且可擷取這些連結的活動以啟用退出目標分析，尤其是當第三方網站在收到此類轉介時負責支付轉介費用時。 由於點按事件依預設會寫入協力廠商系統的記錄檔，因此必須對點按事件連結進行修改，才能在本機擷取該點按事件。 您網站中的第三方連結必須修改如下：

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

必須創 [!DNL PageExit.htm] 建引用的檔案，並且應構造為包含以下指令碼：

```
<html> 
<head> 
 
<script> 
function getExitURLQuery(variable) 
{ 
 
var query = window.location.search.substring(1); 
var vars = query.split("&"); 
for (var i=0; i<vars.length; i++) 
{ 
var pair = vars[i].split("="); 
if (pair[0] == variable) 
{ 
return pair[1]; 
} 
 }  
} 
</script> 
 
<script> 
location.replace(getExitURLQuery("v_eurl")); 
</script>  
 
</head> 
</html>
```

透過對檔案提出 [!DNL PageExit.htm] 要求，會收集v_eurl值以用於分析。 此外，當載 [!DNL PageExit.htm] 入時，它會立即重新導向至指定的v_eurl目標位置。

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_eurl | 與v_eurl查詢字串變數相關聯的值。 此值代表HTML頁面內所存在連結的目標URL。 | v_eurl=www.othersite.com |

