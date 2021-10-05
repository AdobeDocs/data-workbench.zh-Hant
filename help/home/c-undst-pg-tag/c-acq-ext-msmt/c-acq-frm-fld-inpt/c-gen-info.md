---
description: 在網頁中輸入的表單值，可透過使用JavaScript收集並附加至後續請求頁面（表單提交時）的查詢字串中。
title: 一般資訊
uuid: 401816a5-1d95-48e6-bedf-ee2a5dbd2d50
exl-id: 9effc72b-e75f-423c-87ec-6ac25edee8d6
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# 一般資訊{#general-information}

在網頁中輸入的表單值，可透過使用JavaScript收集並附加至後續請求頁面（表單提交時）的查詢字串中。

以下範例中顯示。 在您的HTML頁面中使用的任何表單驗證指令碼之後加入此JavaScript。

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

此範例會將瀏覽器使用者在表單中輸入的值附加至「表單動作」值中指出的後續「thankyou.asp」頁面，如下所示：

```
https://www.myserver.com/thankyou.asp?v_1=John Smith&v_2=Los Angeles&v_3=California&v_4=90210
```

除了[!DNL Sensor]所收集的基線測量資料外，還將利用此請求獲得以下擴展測量資料：

| 收集的資料 | 解釋 | 範例 |
|---|---|---|
| v_1 | 與NAME表單欄位關聯的值 | v_1=John Smith |
| v_2 | 與CITY表單欄位關聯的值 | v_2=洛杉磯 |
| v_3 | 與STATE表單欄位關聯的值 | v_3=加州 |
| v_4 | 與ZIP表單欄位關聯的值 | v_4=90210 |
