---
description: 如果用戶端可透過多個網路（例如透過公司內部網路和網際網路）存取Insight Server，則位址檔案必須為伺服器的每個IP位址定義個別的網路位置。
title: Insight Server 的多個 IP 位址
uuid: 6ed00b47-8ba3-4127-a5db-7e684e573d9c
exl-id: 71654a60-af82-45f2-826b-29ecc7127b0b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 7%

---

# Insight Server 的多個 IP 位址{#multiple-ip-addresses-for-an-insight-server}

如果用戶端可透過多個網路（例如透過公司內部網路和網際網路）存取Insight Server，則位址檔案必須為伺服器的每個IP位址定義個別的網路位置。

例如，如果伺服器[!DNL VS01.myCompany.com]的內部網路上的IP地址為10.2.1.70，而網際網路上的IP地址為65.196.125.167，則地址檔案將包括每個地址的網路位置，如下例所示：

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

當用戶連接到[!DNL Insight Server]時，他們使用NetworkLocation參數（在客戶端用戶介面中）來指定要通過其解析伺服器的公共名稱的網路位置。 例如，給定具有上面所示兩個NetworkLocations的地址檔案，用戶會將NetworkLocation參數設定為&quot;MyCorporate Intranet&quot;以通過內部網路連接到[!DNL Insight Server]，並將「Internet」設定為通過Internet連接到伺服器。
