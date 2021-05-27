---
description: 擷取第三方網站連結上的活動以啟用退出目標分析。
title: 追蹤退出至外部連結次數
uuid: 523f5b4c-4600-4d44-82e7-4a8b2db2d266
exl-id: fd7434e9-cd66-408e-baa9-6a0df4039786
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 6%

---

# 追蹤退出至外部連結次數{#tracking-exits-to-external-links}

擷取第三方網站連結上的活動以啟用退出目標分析。

網頁可包含連結至協力廠商網站，且可擷取這些連結上的活動以啟用退出目標分析，尤其是在第三方網站在收到這類反向連結時負責支付反向連結費用的情況下。 由於點擊事件預設會寫入協力廠商系統的記錄檔，因此必須對連結進行修改，才能在本機擷取點擊事件。 您網站中出現的第三方連結必須修改如下：

```
<A HREF=”http://www.myserver.com/PageExit.htm?v_eurl=http://www.othersite.com”>
```

必須建立引用的[!DNL PageExit.htm]檔案，並且應該進行結構化以包含以下指令碼：

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

借由對[!DNL PageExit.htm]檔案提出要求，便會收集v_eurl值以用於分析。 此外，載入[!DNL PageExit.htm]時，會立即重新導向至指定的v_eurl目標位置。

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_eurl | 與v_eurl查詢字串變數相關聯的值。 此值代表HTML頁面內所呈現連結的目標URL。 | v_eurl=www.othersite.com |
