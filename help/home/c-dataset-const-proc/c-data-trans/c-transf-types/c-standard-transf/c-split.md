---
description: 分割轉換會根據指定的分隔字元，將字串分割為子字串的向量。
title: Split
uuid: 116e8465-8fb1-41eb-9a28-412cee54ab87
exl-id: ea85b095-1306-4938-906d-35d421db6c98
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 3%

---

# 分割{#split}

{{eol}}

分割轉換會根據指定的分隔字元，將字串分割為子字串的向量。

[!DNL Split] 對於從與單個URI查詢名稱值關聯的值集合中提取單個值特別有用。

<table id="table_C97DA4E45DA844FAB8D61AABA22FF809"> 
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
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 套用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 分隔字元 </td> 
   <td colname="col2"> <p>用來將輸入字串分隔為子字串的字串。 長度必須為單一字元。 </p> <p> 如果按住Ctrl鍵並在「分隔字元」參數內按一下滑鼠右鍵，則會出現「插入」功能表。 此菜單包含通常用作分隔符的特殊字元的清單。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入 </td> 
   <td colname="col2"> 值被拆分以建立輸出字串向量的欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> 輸出欄位的名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

請考慮在哪個網站中，當存取與成功購買相關聯的確認頁面時，客戶購買的產品會列為cs-uri查詢值的一部分。 以下是此類字串的範例：

* /checkout/confirmed.asp?prod_selected=B57481,C46355,Z97123

cs-uri-stem欄位用於判斷記錄項目所請求的頁面是否為確認頁面。 客戶購買的產品代碼在cs-uri-query中以逗號分隔的prod_selected名稱值列出。 此 [!DNL Split] 如果cs-uri-stem的值符合中指定的值，則可使用轉換來分割產品代碼，以逗號擷取此資訊 [!DNL String Match] 條件。 請參閱 [字串符合](../../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-f8d132085c6b4500bfbe4515b848142f). 以下轉換詳細說明了此問題的解決方案。

![](assets/cfg_TransformationType_Split.png)

在此，輸出欄位是x-products，可用來建立所需的延伸維度，將購買的產品對應至進行購買的工作階段。
