---
description: 分割轉換會根據指定的分隔字元，將字串分割為子字串的向量。
solution: Analytics
title: 分割
topic: Data workbench
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Split{#split}

分割轉換會根據指定的分隔字元，將字串分割為子字串的向量。

[!DNL Split] 對於從與單個URI查詢名稱值相關聯的值集合中提取單個值特別有用。

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用於將輸入字串分隔為子字串的字串。 長度必須為單一字元。 </p> <p> 如果按住Ctrl鍵並在分隔字元參數內按一下滑鼠右鍵，則會出現「插入」功能表。 此功能表包含常用作分隔字元的特殊字元清單。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 值被分割以建立輸出字串向量的欄位名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 輸出欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

請考慮在網站中，當存取與成功購買相關的確認頁面時，客戶購買的產品會列為cs-uri查詢值的一部分。 以下是此類字串的範例：

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

cs-uri-stem欄位可用來判斷記錄項目所要求的頁面是否為確認頁面。 客戶所購買產品的代碼會列為cs-uri-query中prod_selected名稱的逗號分隔值。 如 [!DNL Split] 果cs-uri-stem的值符合條件中指定的值，則轉換可用來將產品代碼拆分為逗號，以擷取此 [!DNL String Match] 資訊。 請參閱 [字串符合](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f)。 以下轉換將詳細說明此問題的解決方案。

![](assets/cfg_TransformationType_Split.png)

在這裡，輸出欄位是x-products，可用來建立所需的延伸維度，將購買的產品對應至進行購買的工作階段。
