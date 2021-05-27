---
description: Insight Server上安裝的位址檔案包含四個預先定義的網路位置。
title: Insight Server 上安裝的位址檔案
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
exl-id: 12e9bfa2-99ac-4584-b761-38401d1bc3d1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 2%

---

# Insight Server 上安裝的位址檔案{#the-address-file-installed-on-insight-server}

Insight Server上安裝的位址檔案包含四個預先定義的網路位置。

下一節中的步驟說明如何配置此檔案。

```
Locations = vector: 4 items  
  0 = NetworkLocation:  
    Addresses = vector: 1 items 
      0 = AddressDefinition:  
        Address = string:  
        Name = string:  
    Name = string:  
    Parent = string:  
  1 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight 
    Parent = string:  
  2 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Insight Server 
    Parent = string: 
  3 = NetworkLocation:  
    Addresses = vector: 0 items 
    Name = string: Report Server 
    Parent = string:
```

* NetworkLocation 0是一個空的、未命名的網路位置，您編輯該位置以將[!DNL Insight Server]的公共名稱與其IP地址關聯。 如果伺服器有多個IP地址，則建立其他NetworkLocations。
* NetworkLocation 1是[!DNL Insight]網路位置。 如果未顯式設定NetworkLocation參數，[!DNL Insight]將通過此網路位置解析公共名稱。

* NetworkLocation 2是[!DNL Insight Server]網路位置。 當[!DNL Insight Servers]在群集中操作時，它們使用此網路位置解析伺服器間通信的通用名稱。

* NetworkLocation 3是[!DNL Report]伺服器網路位置。 如果未顯式設定NetworkLocation參數，[!DNL Report]將通過此網路位置解析公共名稱。

## 配置地址檔案{#section-10caab9854a244e39b09071946f7bd27}

以下過程說明如何配置地址檔案以定義[!DNL Insight Server]的網路位置（或網路位置）。

1. 導覽至[!DNL Insight Server]安裝目錄（例如[!DNL C:\Adobe\Server\Addresses)]）中的[!DNL Addresses]資料夾。

1. 找到[!DNL server.address]檔案，並更名此檔案以反映伺服器的常用名稱。 例如，如果公用名稱為[!DNL server.mycompany.com]，則可更名檔案[!DNL server.mycompany.com.address]。

1. 在文本編輯器（如記事本）中開啟更名的檔案。
1. 編輯NetworkLocation 0以指定[!DNL Insight Server]的公用名和IP地址，如下所示。 如果您的伺服器有多個IP地址，請使用NetworkLocation 0在本地非可路由網路（例如，其在內部網路上的位置）上指定該伺服器的IP地址。

   ```
   Locations = vector: 3 items 
   0 = NetworkLocation: 
     Addresses = vector: 1 items 
       0 = AddressDefinition: 
         Address = string: IPAddress 
         Name = string: CommonName 
     Name = string: NetworkLocationName 
     Parent = string: 
   ```

<table id="table_02C2A1630CCD40C4A51B314C3CB683F1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於此值…… </th> 
   <th colname="col2" class="entry"> 指定分類的 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>IP 位址</i> </td> 
   <td colname="col2"> <p><span class="keyword"> Insight Server </span>電腦的數值IP位址。 </p> <p>例如: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>公用名稱  </i> </td> 
   <td colname="col2"> <p>指派給<span class="keyword"> Insight Server </span>數位憑證的通用名稱。 </p> <p>範例：<span class="filepath"> server.mycompany.com </span></p> <p>注意：請務必輸入與憑證上顯示的名稱完全相同的名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>網路位置名稱  </i> </td> 
   <td colname="col2"> <p>要分配給此NetworkLocation所表示的常用名稱和IP地址集合的名稱。 該名稱在地址檔案中必須是唯一的。 </p> <p>範例：企業內聯網 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 如果您的[!DNL Insight Server]有其他IP地址，請為每個地址建立其他NetworkLocation。 （一個簡單的方法是製作上面建立的NetworkLocation的副本並更新副本中的IP地址。）

   可以將新的NetworkLocation添加到地址檔案的結尾，或在現有的NetworkLocation定義之間插入它。 (地址檔案中的NetworkLocation位置不重要；但是，[!DNL Insight]、[!DNL Insight Server]和[!DNL Report]伺服器網路位置通常放在檔案的結尾處。)

   添加必要的NetworkLocations後，請執行以下操作重新編號檔案中的項：

   1. 更新「位置」結構的項計數，以匹配檔案中的NetworkLocation定義的總數。 例如，如果檔案包含四個NetworkLocation定義，則「位置」行如下所示：

      ```
      Locations = vector: 4 items
      ```

   1. 更新NetworkLocation項號，以便NetworkLocations的編號從0開始連續（從0開始）。
   有關定義[!DNL Insight Server]且包含兩個IP地址的地址檔案的示例，請參見本節中的示例。

1. 在[!DNL Insight]和[!DNL Report]伺服器網路位置中，編輯下面所示的父參數，以指定[!DNL Insight]和[!DNL Report]用作預設網路位置的NetworkLocation的名稱。 （如需設定Parent參數時看起來的範例，請參閱本節中的範例。）

   ```
   1 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight 
     Parent = string: ClientDefaultNetworkLocation 
   
   3 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Report Server 
     Parent = string: ClientDefaultNetworkLocation
   ```

   如果您的[!DNL Insight Server]只有一個IP地址，因此只有一個NetworkLocation，請將父參數指向該NetworkLocation。 如果您的[!DNL Insight Server]有多個IP地址，請將Parent參數指向定義[!DNL Insight]和[!DNL Report]客戶端最常連接的地址的NetworkLocation。

1. 在[!DNL Insight Server]網路位置中，編輯如下所示的父參數，以指向伺服器在群集中運行時用於解析其他[!DNL Insight Servers]的公共名稱的NetworkLocation。 （雖然除非[!DNL Insight Server]在群集中運行，否則不會使用此網路位置，但即使在單個伺服器配置中，也最好將父參數指向標識伺服器內部IP地址的網路位置。）

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

以下示例顯示已完成的地址檔案。 此檔案定義了五個網路位置。

* NetworkLocation項0和1定義名為「MyCorporateIntranet」和「Internet」的網路位置。 這些網路位置為名為[!DNL VS01.myCompany.com]的伺服器定義兩個不同的IP地址。
* NetworkLocation項2是[!DNL Insight]網路位置。 這是[!DNL Insight]使用的預設網路位置。 在此示例中，[!DNL Insight]網路位置從&quot;Internet&quot; NetworkLocation繼承其AddressDefinitions。

* NetworkLocation項3是[!DNL Insight Server]網路位置。 這是[!DNL Insight Server]在與群集中的其他伺服器通信時使用的預設網路位置。 在此示例中，[!DNL Insight Server]網路位置從&quot;MyCorporate Intranet&quot; NetworkLocation繼承其AddressDefinations。

* NetworkLocation項4是[!DNL Report]伺服器網路位置。 這是[!DNL Report]使用的預設網路位置。 在此示例中，[!DNL Report]伺服器網路位置從&quot;Internet&quot; NetworkLocation繼承其AddressDefinitions。

   ```
   Locations = vector: 5 items 
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
   
     2 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight 
       Parent = string: Internet 
   
     3 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Insight Server 
       Parent = string: MyCorporateIntranet 
   
     4 = NetworkLocation:  
       Addresses = vector: 0 items 
       Name = string: Report Server 
       Parent = string: Internet
   ```
