---
description: Data Workbench運用規則運算式(regex)來執行搜尋和排序操作。
title: 規則運算式
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
exl-id: bb1be6d8-3b7a-47e4-bb29-4a65de99666b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 3%

---

# 規則運算式{#regular-expressions}

{{eol}}

Data Workbench運用規則運算式(regex)來執行搜尋和排序操作。

在 **[!UICONTROL Search]** 欄位，您可以使用通用運算式，依「re：」陳述式執行搜尋，例如：

```
<b>re: *.s</b>
```

<table id="table_BA125AB039794EE382B33003BE4E0AFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元字元 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>. （圓點） </p> </td> 
   <td colname="col2"> <p>比對單一字元，例如： <span class="filepath"> re:x.z </span> 匹配"xyz"或"xxz"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>*（星號） </p> </td> 
   <td colname="col2"> <p>匹配一個或多個字元，例如： <span class="filepath"> re:Z* </span> 匹配"ZZZ"。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? （萬用字元） </p> </td> 
   <td colname="col2"> <p>匹配以前表達式的0或1以強制最小匹配，例如： <span class="filepath"> xy?z </span> 匹配"xy"和"xyz"。 </p> </td> 
  </tr> 
 </tbody> 
</table>

其他常用規則運算式也可用來建立更複雜的搜尋字串。 規則運算式用於所有Data Workbench搜尋欄位，包括查詢實體面板。

請參閱 [規則運算式](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions).
