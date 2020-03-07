---
description: 查詢字串變數可新增至JavaScript請求，以在提出請求時收集其他測量值。
solution: Analytics
title: 取得其他資訊
topic: Data workbench
uuid: 0a8075e9-4986-42c4-b505-3985b433cf8e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 取得其他資訊{#acquiring-additional-information}

查詢字串變數可新增至JavaScript請求，以在提出請求時收集其他測量值。

這些變數可以手動新增，或是透過頁面本身的指令碼新增。

例如，可通過指令碼將可從頁面獲取的附加資訊添加到嵌入式對象中：

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
var v = {}; 
v["_pn"] = "Application Form"; 
v["_1"] = “99.99”; 
v["_2"] = "visa"; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
<noscript> 
 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
<!-- END REFERENCE PAGE TAG-->
```

在此範例中，v_1和v_2的指令碼變數可從網頁內的其他函式衍生。 變數已插入為範例。 除了每次請求所取得的基準測量值外，以下延伸測量值也會隨上述URL請求而取得：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_pn= | 與v_pn查詢字串變數相關聯的值 | v_pn=應用程式表單 |
| v_1= | 與v_1查詢字串變數相關聯的值 | v_1=99.99 |
| v_2= | 與v_2查詢字串變數相關聯的值 | v_2=visa |

