---
description: 時間維度可讓您根據您為「輸入時間」（1970年）參數所指定的任何時間戳記欄位，建立一組定期或絕對的本機時間維度（例如日、周中的某天、一天中的某小時、保留時間等）。
solution: Analytics
title: 時間維度
topic: Data workbench
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 時間維度{#time-dimensions}

時間維度可讓您根據您為「輸入時間」（1970年）參數所指定的任何時間戳記欄位，建立一組定期或絕對的本機時間維度（例如日、周中的某天、一天中的某小時、保留時間等）。

在定義時間維度時，您也可以選擇以週一以外的日期作為一週的開始，只要指定「週起始日」參數即可。只要維度名稱不同，您就可以在資料集中定義多組時間維度。

時間維由以下參數定義：

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 維度在資料工作台中顯示的描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於擴展維的注釋。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 維度 </td> 
   <td colname="col2"> <p>您可以為下列任一句點指定維度名稱： </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> 日 </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> 星期 </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> 小時 </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> 小時 </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> 月 </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> 週 </li> 
     </ul> </p> <p> 您在此處輸入的名稱是顯示在維度選單和資料工作台視覺化中的名稱。 如果將時間維的名稱保留為空，則不會在資料集中建立維。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否出現在資料工作台介面中。 依預設，此參數會設為false。 例如，如果維度僅用作度量的基礎，您可以將此參數設為true，以隱藏資料工作台顯示的維度。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入時間（1970年） </td> 
   <td colname="col2"> <p>用作輸入的時間戳記欄位名稱。 </p> <p> <p>注意： 欄位的值必須代表自1970年1月1日00:00:01以來的秒數。 如果輸入時間不是有效時間（1970到2037），轉換程式將失敗，而資料工作台伺服器將產生錯誤。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數的維度都可以是父項維度。 對於Web資料，父代為「工作階段」。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 周開始日 </td> 
   <td colname="col2"> <p>用作一週中第一天的日。 </p> <p> 此參數會影響「周」維度、「週日」維度，以及以周定義的任何報告時間維度。 </p> </td> 
   <td colname="col3"> 週一 </td> 
  </tr> 
 </tbody> 
</table>

此範例會根據使用者定義的輸入欄位x-time-1970建立一組時間維度。 時間維度集名為「作業時間」。 由於每個維的父代是「會話」維，因此時間維的每個元素都對應於會話開始的時間。 「周開始日」參數指定「周」維度的每週從星期一開始。

![](assets/cfg_Transformation_Dim_TimeDim.png)

