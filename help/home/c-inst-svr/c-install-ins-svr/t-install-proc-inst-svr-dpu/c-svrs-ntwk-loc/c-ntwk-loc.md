---
description: 從概念上講，地址檔案的用途與聯網電腦上的ETC&bsol;HOSTS檔案相同。
title: 網路位置
uuid: a2097eca-dd75-4d43-b8a8-fb4c768df38d
exl-id: 938217da-8935-4f2a-b5f8-9afc1dd489f3
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# 網路位置{#network-locations}

{{eol}}

從概念上講，地址檔案的用途與聯網電腦上的ETC&amp;bsol;HOSTS檔案相同。

但是，與描述單個名稱集合的HOSTS檔案不同，地址檔案包含多個名稱集合，稱為網路位置。

網路位置是地址定義的命名集合。 集合中的每個地址定義都會將通用名稱與IP地址關聯。

在地址檔案中，網路位置被定義在稱為NetworkLocation的結構中。 以下示例中的NetworkLocation定義了名為「MyCorporate Intranet」的網路位置。 它包含映射公用名稱的地址定義 [!DNL VS01.myCompany.com] 至IP位址「10.2.1.70」。

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
```

如上例所示， NetworkLocation結構由三個主要參陣列成：

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
   <td colname="col2"> 定義零個或多個AddressDefinitions。 每個AddressDefinition都將一個通用名稱與一個IP地址關聯。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 為NetworkLocation指定名稱。 分配給NetworkLocation的名稱在地址檔案中必須是唯一的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 父級 </td> 
   <td colname="col2"> <p>指定其成員包含在此NetworkLocation中的其他NetworkLocation的名稱。 此參數使一個NetworkLocation能夠擴展另一個。 </p> <p>您可以將Parent參數設定為「DNS」，以將NetworkLocation擴展到客戶端的正常DNS系統。 </p> <p>範例：父=字串：DNS </p> <p>當DNS是父代時，當客戶機無法通過NetworkLocation解析該名稱時，客戶機將嘗試使用客戶機的DNS系統解析公共名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>
