---
description: 資料工作台運用規則運算式(regex)來搜尋和排序作業。
title: 規則運算式
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 2%

---

# 規則運算式{#regular-expressions}

資料工作台運用規則運算式(regex)來搜尋和排序作業。

在&#x200B;**[!UICONTROL Search]**&#x200B;欄位中，您可以使用常用運算式，依&quot;re:&quot;陳述式執行搜尋，例如：

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元字元 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. （點） </p> </td> 
   <td colname="col2"> <p>符合單一字元，例如：<span class="filepath"> re:x.z </span>與"xyz"或"xxz"相符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>*（星號） </p> </td> 
   <td colname="col2"> <p>匹配一個或多個字元，例如：<span class="filepath"> re:Z* </span>與"ZZZ"匹配。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? （萬用字元） </p> </td> 
   <td colname="col2"> <p>匹配上一個表達式的0或1以強制最小匹配，例如：<span class="filepath"> xy?z </span>與"xy"和"xyz"匹配。 </p> </td> 
  </tr> 
 </tbody> 
</table>

其他常用規則運算式也可用來建立更複雜的搜尋字串。 規則運算式可用於所有Data Workbench搜尋欄位，包括查詢實體面板。

請參閱[規則運算式](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions)的深入資訊。
