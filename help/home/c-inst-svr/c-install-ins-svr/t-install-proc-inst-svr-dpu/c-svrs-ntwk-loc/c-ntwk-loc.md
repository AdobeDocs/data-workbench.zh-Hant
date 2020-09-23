---
description: 從概念上講，地址檔案與聯網電腦上的ETC&bsol;HOSTS檔案有相同的用途。
solution: Analytics
title: 網路位置
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---


# 網路位置{#network-locations}

從概念上講，地址檔案與聯網電腦上的ETC&amp;bsol;HOSTS檔案有相同的用途。

但是，與描述單個名稱集合的HOSTS檔案不同，地址檔案包含多個名稱集合，稱為網路位置。

網路位置是地址定義的命名集合。 集合中的每個地址定義都將公用名稱與IP地址關聯。

在地址檔案中，網路位置定義在稱為NetworkLocation的結構中。 以下示例中的NetworkLocation定義了名為&quot;MyCorporate Intranet&quot;的網路位置。 它包含將公用名稱映射 [!DNL VS01.myCompany.com] 到IP地址&quot;10.2.1.70&quot;的地址定義。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

如上例所示，NetworkLocation結構由三個主要參陣列成：

<table id="table_9142A0EFA15E4C37975E7ACE234F6FDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> 定義零個或多個AddressDefinitions。 每個AddressDefinition都將公用名稱與IP位址關聯。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 為NetworkLocation指定名稱。 分配給NetworkLocation的名稱在地址檔案中必須是唯一的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父代 </td> 
   <td colname="col2"> <p>指定其成員包含在此NetworkLocation中的另一個NetworkLocation的名稱。 此參數可讓一個NetworkLocation擴展另一個。 </p> <p>您可以將Parent參數設為"DNS"，將NetworkLocation擴充至用戶端的一般DNS系統。 </p> <p>範例：父=字串：DNS </p> <p>當DNS為父代時，當客戶端無法透過NetworkLocation解析該名稱時，會嘗試使用客戶端機器的DNS系統解析公用名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>
