---
description: 數學轉換允許對日誌條目中的欄位使用算術運算。
solution: Analytics
title: 數學
topic: Data workbench
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 數學{#math}

數學轉換允許對日誌條目中的欄位使用算術運算。

這些操作可包括小數整數和浮點常數。

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 運算式 </td> 
   <td colname="col2"> <p>描述要執行的計算的算術表達式。 </p> <p> 您可以使用下列任何操作和函式，也可以在表達式中合併欄位名： </p> <p> 操作 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> 加法 (+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> 減法 (-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> 乘法 (*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> 除法 (/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> 剩餘(%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> 乘冪 (^) </li>
     </ul></p> <p>函數 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sgn(x)。 如果x為正數，則傳回1；如果x為零，則傳回0；如果x為負數，則傳回-1。 </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x)。 傳回x的絕對值。 </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> 樓層(x)。 傳回小於或等於x的最大整數。 </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x)。 傳回最接近x的整數。 </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x)。 傳回x底b的對數。 </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> 最小值(x,y,...)。 傳回其所有引數中最小的值。 </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...) 傳回其所有引數中最大的引數。 </li>
     </ul></p> </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 包含算術運算結果的欄位的名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
 </tbody> 
</table>

在此範例中，使用從網站流量收集到的資料欄位，從x-timestamp中減去x-last-pv-timestamp，然後新增1，即可計算名為x-page-duration的新欄位。 只有當使用者定義的欄位x-last-pv-timestamp（代表訪客最後一頁檢視的時間戳記）已填入或「非空白」時，才會計算輸出。

![](assets/cfg_TransformationType_Math.png)

有關該條件的信 [!DNL Not Empty] 息，請參 [閱條件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。