---
description: 「比較」條件和「範圍」條件要求您指定要對條件進行比較的類型。
title: 測試操作的測試類型
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 2%

---

# 測試操作的測試類型{#test-types-for-test-operations}

{{eol}}

「比較」條件和「範圍」條件要求您指定要對條件進行比較的類型。

下表說明可用類型( [!DNL LEXICAL], [!DNL NUMERIC]，和 [!DNL DATETIME])。

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
   <td colname="col2"> <p>首先，將輸入欄位轉換為整數。 如果不可能，則使用零值。 僅當生成的整數輸入值大於或等於指定最小值且小於或等於指定最大值時，測試才返回true。 </p> </td> 
   <td colname="col3"> <p>如果最小值或最大值欄位中的一個留空，則系統將使用適當的最小值或最大值，該值可用於64位帶符號的整數。 </p> <p> 如果條件中指定的最小值或最大值未成功剖析為整數值，系統會取代零值，且不會停止處理資料集。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>首先將輸入欄位轉換為日期。 如果輸入欄位無法轉換為有效日期，條件測試會傳回false。 如果欄位可轉換為日期，則只有在輸入日期落在指定的最小日期之後，以及指定的最大日期之前，測試才會傳回true。 </p> </td> 
   <td colname="col3"> <p>如果最小和最大日期無效，則不會建構資料集。 </p> <p> 如果未提供最小日期或最大日期，則系統會適當替換最小日期（1600年1月1日）或最大日期（24世紀的某個時間）。 </p> <p> Adobe建議對 <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 2013年1月1日HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 2013年1月1日HH:MM:SS GMT </li> 
    </ul> <p> 若未指定，時區會預設為GMT。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> 辭匯</span> </p> </td> 
   <td colname="col2"> <p>僅當輸入欄位詞法上大於或等於指定為最小值的字串且小於或等於最大值中指定的字串時，才返回true。 </p> </td> 
   <td colname="col3"> <p>詞法比較使用從左到右移動的字串中字元的ASCII值來比較字元。 對於第一個不符的字元，ASCII值較大的字元會視為兩者中的較大者。 如果一個字串比另一個字串短，但直到該時間點為止，所有字元都相同，則長字串被視為兩者中的大者。 如果字串是等同字元的字元，且長度完全相同，則在詞法上視為等同字元。 </p> </td> 
  </tr> 
 </tbody> 
</table>
