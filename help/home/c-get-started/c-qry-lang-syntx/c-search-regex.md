---
description: 資料工作台運用規則運算式(regex)來搜尋和排序作業。
solution: Analytics
title: 規則運算式
topic: Data workbench
uuid: dc8c1e88-4d95-4011-8a38-70fae0c5cf6d
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Regular expressions{#regular-expressions}

資料工作台運用規則運算式(regex)來搜尋和排序作業。

在欄位 **[!UICONTROL Search]** 中，您可以使用常用運算式，依&quot;re:&quot;陳述式執行搜尋，例如：

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
   <td colname="col1"> <p>。（點） </p> </td> 
   <td colname="col2"> <p>符合單一字元，例如： <span class="filepath"> re:x.z與 </span> "xyz"或"xxz"相符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>*（星號） </p> </td> 
   <td colname="col2"> <p>匹配一個或多個字元，例如： <span class="filepath"> re:Z*與 </span> "ZZZ"相符。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>? （萬用字元） </p> </td> 
   <td colname="col2"> <p>匹配上一個表達式的0或1以強制最小匹配，例如： <span class="filepath"> xy?z </span> 與"xy"和"xyz"匹配。 </p> </td> 
  </tr> 
 </tbody> 
</table>

其他常用規則運算式也可用來建立更複雜的搜尋字串。 規則運算式會用於所有「資料工作台」搜尋欄位，包括查詢實體面板。

請參閱規則運算式的深 [入資訊](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html#Regular_Expressions)。
