---
description: 數學轉換允許對日誌條目內的欄位使用算術運算。
title: Math
uuid: 9e1a5950-8fb2-48e9-b9a1-82c5165fba10
exl-id: d8b9cacd-67d1-447c-94dd-7028aa371dfa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 5%

---

# 數學{#math}

{{eol}}

數學轉換允許對日誌條目內的欄位使用算術運算。

操作可包含小數整數和浮點常數。

<table id="table_FDF3DDF1960E43E391A67C9DC2A0E302"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 套用此轉換的條件。 </td> 
   <td colname="col3"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> 運算式 </td> 
   <td colname="col2"> <p>描述要執行的計算的算術表達式。 </p> <p> 您可以使用下列任何操作和函式，並且可以將欄位名稱併入表達式中： </p> <p> 運作 
     <ul id="ul_DB5915FADA0A41A3B11F1F48615F40A9">
      <li id="li_CA9EA97243F04760A81313C17EE057B3"> 加(+) </li>
      <li id="li_908A272EBA2340098C20F22AA8D9ED26"> 減(-) </li>
      <li id="li_C62257FF3AAB436D9148BBEA441621D7"> 乘(*) </li>
      <li id="li_B5A9EAB3E49D4CB9A297172199F23542"> 除(/) </li>
      <li id="li_D2D2B51DB2C8412A9B6F9D5F3CC03F8A"> 余數(%) </li>
      <li id="li_07E7E368FFD2437A852B785E159848E5"> 乘冪 (^) </li>
     </ul></p> <p>函數 
     <ul id="ul_E335AE8D684340AA998C4A2633FFDEE1">
      <li id="li_E036FF0B5DF244DDBFEDA9BFEDC62251"> sgn(x)。 如果x為正，則傳回1；如果x為零，則傳回0；如果x為負，則傳回–1。 </li>
      <li id="li_90CD8899DDC14778A95930C2768C82BC"> abs(x)。 傳回x的絕對值。 </li>
      <li id="li_F4AF23F343F74BD88B7166B1C2BB065E"> 第(x)層。 傳回小於或等於x的最大整數。 </li>
      <li id="li_A31379A3659240C3A629BFAF19A6DDF1"> round(x)。 將最接近的整數傳回為x。 </li>
      <li id="li_9C0A0F3A4A304026B543F2A64B98B922"> log(b,x)。 傳回x底b的對數。 </li>
      <li id="li_124D62C2CA5A42CBBCC5DB18FAA8920E"> 最小值(x,y,...) 傳回其所有引數的最小值。 </li>
      <li id="li_3B7B9FC1C0BF4E7688F9F49130B97B7F"> max(x,y,...) 傳回其所有引數中最大的。 </li>
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

在此範例中，使用從網站流量收集的資料欄位，透過從x-timestamp減去x-last-pv-timestamp，然後新增1，來計算名為x-page-duration的新欄位。 只有在填入使用者定義的欄位x-last-pv-timestamp（代表訪客上次頁面檢視的時間戳記）或「非空白」時，才會計算輸出。

![](assets/cfg_TransformationType_Math.png)

如需 [!DNL Not Empty] 條件，請參閱 [條件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).
