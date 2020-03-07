---
description: IPLookup轉換會擷取IP地理位置或IP地理情報資料（由此類資料的任何供應商提供，並由Adobe轉換為專屬格式），並將資料轉換為可用於分析的地理資訊。
solution: Analytics
title: IPLookup
topic: Data workbench
uuid: 6fccee39-761f-4854-a7fd-3f8b453e0698
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IPLookup{#iplookup}

IPLookup轉換會擷取IP地理位置或IP地理情報資料（由此類資料的任何供應商提供，並由Adobe轉換為專屬格式），並將資料轉換為可用於分析的地理資訊。

「新 [!DNL IPLookup] 增> *轉換類型*」菜單中列出了兩個轉換：

* [!DNL IPLookup] Quova for [!DNL IP geo-location] data

* [!DNL IPLookup] Digital Envoy for [!DNL IP geo-intelligence] data

定義轉換 [!DNL IPLookup] 時，請為您或資料選擇適 [!DNL IP geo-location] 當的轉 [!DNL IP geo-intelligence] 換。

<table id="table_C438A30AB5E64160A5C486D6887B1D7E"> 
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
   <td colname="col1"> 檔案 </td> 
   <td colname="col2"> 查閱檔案的路徑和檔案名稱。 相對路徑與資料工作台伺服器的安裝目錄有關。 此檔案通常位於資料工作台伺服器安裝目錄內的「查閱」目錄中。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> IP 位址 </td> 
   <td colname="col2"> 讀取IP位址的欄位。 </td> 
   <td colname="col3"> c-ip </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出 </td> 
   <td colname="col2"> <p>輸出字串的名稱。 </p> <p> IPLookup <span class="wintitle"> Quova和</span> IPLookup <span class="wintitle"></span> Digital Envoy轉換具有不同的輸出參數。 請務必對IP查閱資料使用適當的轉換。 </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

在此範例中， [!DNL IP geo-location] 資料(在查閱檔案 [!DNL Quova.bin]中)可用來建立列出的輸出欄位。 輸出（AOL、ASN、區域代碼等）可用來建立維度，以便對訪客流量進行地理分析。

![](assets/cfg_TransformationType_IPLookup.png)

