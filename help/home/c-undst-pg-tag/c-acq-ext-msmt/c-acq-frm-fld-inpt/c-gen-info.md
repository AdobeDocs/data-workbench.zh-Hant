---
description: 在網頁中輸入的表單值可以透過使用JavaScript來收集並附加至後續請求頁面（表單提交時）的查詢字串中。
solution: Analytics
title: 一般資訊
topic: Data workbench
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 一般資訊{#general-information}

在網頁中輸入的表單值可以透過使用JavaScript來收集並附加至後續請求頁面（表單提交時）的查詢字串中。

以下範例中顯示此點。 在HTML頁面中使用的任何表單驗證指令碼之後加入此JavaScript。

```
<html> 
<head> 
</head> 
<script language="JavaScript"> 
 
function AppendFormValues() 
{ 
 
for(var i = 0; i < document.formname.length; i++) 
{ 
var item = document.formname.elements[i]; 
var formitem = “v_”+i; 
var formvalue = item.value; 
formvalues += formitem + '=' + formvalue + '&'; 
} 
document.formname.action = document.formname.action + '?' + formvalues; 
 
} 
</script> 
<body> 
<form name="formname" action="thankyou.asp" method="POST" onSubmit="AppendFormValues();"> 
<input name="NAME" size="50" value=""></input>name<br/> 
<input name="CITY" size="50" value=""></input>city<br/> 
<input name="STATE" size="50" value=""></input>state<br/> 
<input name="ZIP" size="10" value=""></input>zip<br /> 
<input type="submit" name="submit" value="submit"/> 
</body> 
</html> 
```

此示例將瀏覽器用戶在表單中輸入的值附加到FORM操作值中指示的後續「tankyou.asp」頁，如下所示：

```
http://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

除了由下列人員收集的基線測量值外，還可使用此請求取得下列延伸測量值 [!DNL Sensor]:

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與NAME表單欄位關聯的值 | v_1=John Smith |
| v_2 | 與CITY表單欄位關聯的值 | v_2=洛杉磯 |
| v_3 | 與STATE表單欄位關聯的值 | v_3=加州 |
| v_4 | 與ZIP表單欄位關聯的值 | v_4=90210 |

