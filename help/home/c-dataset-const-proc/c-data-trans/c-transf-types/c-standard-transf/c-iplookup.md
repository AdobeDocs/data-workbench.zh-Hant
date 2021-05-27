---
description: IPLookup轉換採用IP地理位置或IP地理智慧資料(由此類資料的任何供應商提供，並通過Adobe轉換為專有格式)，並將資料轉換為可用於分析的地理資訊。
title: IPLookup
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
exl-id: 3e9dba44-8d31-49af-8ce0-fecaf92edeb7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 4%

---

# IPLookup{#iplookup}

IPLookup轉換採用IP地理位置或IP地理智慧資料(由此類資料的任何供應商提供，並通過Adobe轉換為專有格式)，並將資料轉換為可用於分析的地理資訊。

新增> *轉換類型*功能表中列出兩個[!DNL IPLookup]轉換：

* [!DNL IPLookup] 資料引 [!DNL IP geo-location] 用

* [!DNL IPLookup] Digital Envoy for  [!DNL IP geo-intelligence] data

定義[!DNL IPLookup]轉換時，請為[!DNL IP geo-location]或[!DNL IP geo-intelligence]資料選擇適當的轉換。

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
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
   <td colname="col1"> 檔案 </td> 
   <td colname="col2"> 查閱檔案的路徑和檔案名。 相對路徑與Data Workbench伺服器的安裝目錄有關。 此檔案通常位於Data Workbench伺服器安裝目錄的「查閱」目錄中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP 位址 </td> 
   <td colname="col2"> 讀取IP位址的欄位。 </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> <p>輸出字串的名稱。 </p> <p> <span class="wintitle"> IPLookup</span> Quova和<span class="wintitle"> IPLookup</span> Digital Envoy轉換具有不同的輸出參數。 請務必為IP查閱資料使用適當的轉換。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

在此示例中，[!DNL IP geo-location]資料（在查找檔案[!DNL Quova.bin]中）用於建立列出的輸出欄位。 輸出（AOL、ASN、區域代碼等）可用來建立訪客流量地理分析的維度。

![](assets/cfg_TransformationType_IPLookup.png)
