---
description: 安裝在Insight Server上的位址檔案包含四個預先定義的網路位置。
solution: Insight
title: Insight Server上安裝的位址檔案
uuid: a58d36d8-e1a3-43e7-91c5-c57351e1be49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Insight Server上安裝的位址檔案{#the-address-file-installed-on-insight-server}

安裝在Insight Server上的位址檔案包含四個預先定義的網路位置。

下一節中的過程介紹如何配置此檔案。

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

* NetworkLocation 0是一個空的未命名網路位置，您可編輯該網路位置以將您的公共名稱與 [!DNL Insight Server] 其IP地址關聯。 如果伺服器有多個IP地址，則可以建立其他NetworkLocations。
* NetworkLocation 1是網 [!DNL Insight] 絡位置。 如果未明確設定NetworkLocation參數，請通過 [!DNL Insight] 此網路位置解析公共名稱。

* NetworkLocation 2是網 [!DNL Insight Server] 絡位置。 在群 [!DNL Insight Servers] 集中操作時，它們使用此網路位置來解析伺服器間通信的通用名稱。

* NetworkLocation 3是伺服器 [!DNL Report] 網路位置。 如果未明確設定NetworkLocation參數，請通過 [!DNL Report] 此網路位置解析公共名稱。

## 配置地址檔案 {#section-10caab9854a244e39b09071946f7bd27}

以下過程介紹如何配置地址檔案以定義網路位置（或網路位置） [!DNL Insight Server]。

1. 導覽至 [!DNL Addresses] 您所安裝目錄中的檔 [!DNL Insight Server] 案夾(例如 [!DNL C:\Adobe\Server\Addresses)]。

1. 找到檔 [!DNL server.address] 案並重新命名此檔案，以反映伺服器的常用名稱。 例如，如果公用名稱為 [!DNL server.mycompany.com]，則可更名檔案 [!DNL server.mycompany.com.address]。

1. 在文本編輯器（如記事本）中開啟更名的檔案。
1. 編輯NetworkLocation 0以指定的公用名稱和IP地址，如 [!DNL Insight Server] 下所示。 如果您的伺服器有多個IP位址，請使用NetworkLocation 0在本端非可路由網路（例如，其在內部網路上的位置）上指定伺服器的IP位址。

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
   <td colname="col2"> <p>Insight Server機器的數 <span class="keyword"> 值IP位 </span> 址。 </p> <p>例如: 192.168.124.176 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>通用名稱 </i> </td> 
   <td colname="col2"> <p>指派給 <span class="keyword"> Insight Server數位憑證的公用名稱 </span>。 </p> <p>範例： <span class="filepath"> server.mycompany.com </span></p> <p>注意：請務必鍵入此名稱，其外觀與憑證上所顯示的相同。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>網路位置名稱 </i> </td> 
   <td colname="col2"> <p>要分配給此NetworkLocation代表的通用名稱和IP地址集合的名稱。 該名稱在地址檔案中必須是唯一的。 </p> <p>範例：企業內部網路 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 如果您 [!DNL Insight Server] 有其他IP位址，請為每個位址建立額外的NetworkLocation。 （要做到這一點，一個簡單的方法是製作上面建立的NetworkLocation副本，並更新副本中的IP地址。）

   您可以將新的NetworkLocation添加到地址檔案的末尾，或在現有的NetworkLocation定義之間插入。 (NetworkLocation在地址檔案中的位置不重要；但是， [!DNL Insight]、 [!DNL Insight Server]和 [!DNL Report] Server NetworkLocations通常放在檔案的末尾。)

   在添加了必要的NetworkLocations後，請執行下列操作以重新編號檔案中的項目：

   1. 更新「位置」結構的項目計數，以匹配檔案中的NetworkLocation定義總數。 例如，如果檔案包含四個NetworkLocation定義，則「位置」行如下所示：

      ```
      Locations = vector: 4 items
      ```

   1. 更新NetworkLocation項目編號，以便NetworkLocations按順序編號（從0開始）。
   有關定義具有兩個IP地址的地址 [!DNL Insight Server] 檔案的示例，請參見本節中的示例。

1. 在和服 [!DNL Insight] 務器網 [!DNL Report] 絡位置中，編輯如下所示的父參數，以指定NetworkLocation的名稱，並 [!DNL Insight] 將其用 [!DNL Report] 作預設網路位置。 （有關配置父參數時其外觀的示例，請參閱本節中的示例。）

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

   如果您 [!DNL Insight Server] 有單個IP地址，因此只有一個NetworkLocation ，請將Parent參數指向該NetworkLocation。 如果您 [!DNL Insight Server] 有多個IP位址，請將Parent參數指向NetworkLocation，該NetworkLocation定義您和客戶端最常連 [!DNL Insight] 接 [!DNL Report] 的地址。

1. 在網 [!DNL Insight Server] 絡位置中，編輯如下所示的父參數，以指向伺服器在群集中操作時用來解析其他公共名稱的 [!DNL Insight Servers] NetworkLocation。 （雖然除非在叢集中運作，否則不會使用此網路位置，但是，即使在單一伺服器組態中，也最好將「上層」參數指向識別伺服器內部IP位址的網路位置。） [!DNL Insight Server]

   ```
   2 = NetworkLocation:  
     Addresses = vector: 0 items 
     Name = string: Insight Server 
     Parent = string: ServerDefaultNetworkLocation
   ```

以下示例顯示一個已完成的地址檔案。 此檔案定義了五個網路位置。

* NetworkLocation項目0和1定義了名為&quot;MyCorporateIntranet&quot;和&quot;Internet&quot;的網路位置。這些網路位置為名為的伺服器定義了兩個不同的IP地址 [!DNL VS01.myCompany.com]。
* NetworkLocation項目2是網路 [!DNL Insight] 位置。 這是使用的預設網路位置 [!DNL Insight]。 在此示例中，網 [!DNL Insight] 絡位置從&quot;Internet&quot; NetworkLocation繼承其AddressDefinitions。

* NetworkLocation項目3是網路 [!DNL Insight Server] 位置。 這是與群集中的其 [!DNL Insight Server] 他伺服器通信時使用的預設網路位置。 在此示例中，網 [!DNL Insight Server] 絡位置從「MyCorporate Intranet」 NetworkLocation繼承其AddressDefinition。

* NetworkLocation項目4是伺服器 [!DNL Report] 網路位置。 這是使用的預設網路位置 [!DNL Report]。 在此示例中，服 [!DNL Report] 務器網路位置繼承其「Internet」 NetworkLocation的AddressDefinitions。

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

