---
description: 時間維度可讓您根據您為「輸入時間」（1970年）參數指定的任何時間戳記欄位，建立一組定期或絕對的當地時間維度（例如日、星期、小時、保留時間等）。
title: 時間維度
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
exl-id: f9534b24-3a16-4220-bac2-bc541e121005
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 11%

---

# 時間維度{#time-dimensions}

時間維度可讓您根據您為「輸入時間」（1970年）參數指定的任何時間戳記欄位，建立一組定期或絕對的當地時間維度（例如日、星期、小時、保留時間等）。

在定義時間維度時，您也可以選擇以週一以外的日期作為一週的開始，只要指定「週起始日」參數即可。只要維度的名稱不同，您就可以在資料集中定義多組時間維度。

時間維度由下列參數定義：

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> Data Workbench中顯示的維度描述性名稱。 維度名稱不能包含連字型大小(-)。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。延伸維度的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 維度 </td> 
   <td colname="col2"> <p>您可以為以下任何句點指定維名稱： </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> 日 </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> 星期 </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> 小時 </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> 小時 </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> 月 </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> 週 </li> 
     </ul> </p> <p> 您在此處輸入的名稱是顯示在Data Workbench中維度功能表和視覺效果中的名稱。 如果將時間維度的名稱保留為空白，系統不會在資料集中建立維度。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏 </td> 
   <td colname="col2"> 判斷維度是否顯示在Data Workbench介面中。 此參數預設會設為false。 例如，如果維度僅作為量度的基礎，您可以將此參數設為true，以便在Data Workbench顯示中隱藏維度。 </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入時間（1970年） </td> 
   <td colname="col2"> <p>要作為輸入的時間戳記欄位的名稱。 </p> <p> <p>注意： 欄位的值必須代表自1970年1月1日(00:00:01)起的秒數。 如果輸入時間不是有效時間（1970到2037年），轉換程式將會失敗，而Data Workbench伺服器會產生錯誤。 </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父級 </td> 
   <td colname="col2"> 父維的名稱。 任何可計數維度都可以是父維度。 若為Web資料，父項為「工作階段」。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 周開始日 </td> 
   <td colname="col2"> <p>用作一週中的第一天的日。 </p> <p> 此參數會影響「周」維度、「週日」維度，以及以周為單位定義的任何報表時間維度。 </p> </td> 
   <td colname="col3"> 週一 </td> 
  </tr> 
 </tbody> 
</table>

此示例根據用戶定義的輸入欄位x-time-1970建立一組時間維。 時間維度集名為「工作階段時間」。 因為每個維的父級是「工作階段」維度，因此時間維度的每個元素都與工作階段開始的時間相對應。 「周開始日」參數指定「周」維的每週從星期一開始。

![](assets/cfg_Transformation_Dim_TimeDim.png)
