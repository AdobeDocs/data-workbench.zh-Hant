---
description: 「比較」條件和「範圍」條件要求您指定要為條件進行的比較類型。
title: 測試操作的測試類型
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# 測試操作的測試類型{#test-types-for-test-operations}

「比較」條件和「範圍」條件要求您指定要為條件進行的比較類型。

下表說明可用類型（[!DNL LEXICAL]、[!DNL NUMERIC]和[!DNL DATETIME]）。

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 測試類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 附註 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 整數</span> </p> </td> 
   <td colname="col2"> <p>首先將輸入欄位轉換為整數。 如果不可能，則使用零值。 只有當產生的整數輸入值大於或等於指定的最小值且小於或等於指定的最大值時，測試才會傳回true。 </p> </td> 
   <td colname="col3"> <p>如果最小或最大欄位中的任一欄位保留為空，則系統將使用適當的最小或最大值，可用於64位有符號的整數。 </p> <p> 如果條件中指定的最小值或最大值未成功解析為整數值，系統將替換零，並且不停止處理資料集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>首先將輸入欄位轉換為日期。 如果輸入欄位無法轉換成有效日期，條件測試會傳回false。 如果欄位可轉換成日期，則只有在輸入日期落在指定的最小日期或之後，且在指定的最大日期之前，測試才會傳回true。 </p> </td> 
   <td colname="col3"> <p>如果最小和最大日期無效，則不構建資料集。 </p> <p> 如果未提供最小或最大日期，系統會適當地替換最小日期（1600年1月1日）或最大日期（24世紀的某個時候）。 </p> <p> Adobe建議對<span class="wintitle"> DATETIME</span>使用下列格式之一： </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 2013年1月1日美國東部夏令時間 </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 2013年1月1日HH:MM:SS GMT </li> 
    </ul> <p> 如果未指定，時區預設為GMT。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 辭彙</span> </p> </td> 
   <td colname="col2"> <p>僅當輸入欄位在詞法上大於或等於指定為最小值的字串且小於或等於最大值中指定的字串時，才返回true。 </p> </td> 
   <td colname="col3"> <p>辭彙比較使用從左到右移動的字串中字元的ASCII值來比較字元。 對於不匹配的第一個字元，ASCII值較大的字元被視為兩個字元中的較大字元。 如果一個字串比另一個字串短，但直到該時段為止，所有字元都相同，則長字串會被視為兩者中的較大字元。 如果字串是等效字元的字元，且長度完全相同，則從語法上來說，這些字串是等效字元。 </p> </td> 
  </tr> 
 </tbody> 
</table>
