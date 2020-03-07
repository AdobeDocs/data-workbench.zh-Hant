---
description: 如果客戶端可以透過多個網路（例如透過公司內部網路和網際網路）到達Insight Server，則位址檔案必須為伺服器的每個IP位址定義個別的網路位置。
solution: Insight
title: Insight Server的多個IP位址
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Server的多個IP位址{#multiple-ip-addresses-for-an-insight-server}

如果客戶端可以透過多個網路（例如透過公司內部網路和網際網路）到達Insight Server，則位址檔案必須為伺服器的每個IP位址定義個別的網路位置。

例如，如果服 [!DNL VS01.myCompany.com] 務器內部網路上的IP地址為10.2.1.70，而Internet上的IP地址為65.196.125.167，則地址檔案將包括每個地址的網路位置，如下例所示：

```
0 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 10.2.1.70
      Name = string: VS01.myCompany.com
  Name = string: MyCorporateIntranet
  Parent = string: 
1 = NetworkLocation: 
  Addresses = vector: 1 items
    0 = AddressDefinition: 
      Address = string: 65.196.125.167
      Name = string: VS01.myCompany.com
  Name = string: Internet
  Parent = string:
```

當使用者連線至 [!DNL Insight Server]某個網路時，他們會使用NetworkLocation參數（在用戶端使用者介面中）來指定要解決伺服器公用名稱的網路位置。 例如，假設有一個地址檔案，上面顯示了兩個NetworkLocations ，用戶會將NetworkLocation參數設定為「MyCorporate Intranet」以通過內部網路連接到 [!DNL Insight Server] ，並將「Internet」設定為通過Internet連接到伺服器。