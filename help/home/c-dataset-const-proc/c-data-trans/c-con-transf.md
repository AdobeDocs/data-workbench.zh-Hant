---
description: 表格顯示建構轉換時應用的慣例。
title: 建構轉換的慣例
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# 建構轉換的慣例{#conventions-for-constructing-transformations}

表格顯示建構轉換時應用的慣例。

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 《公約》 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 循序執行 </td> 
   <td colname="col2"> <p>資料集配置檔案中的轉換將按順序應用到日誌條目（即按配置檔案中列出的順序）。 因此，必須按其輸出作為其他轉換的輸入的順序列出轉換。 更具體地說，如果將某個轉換的輸出用作另一個轉換的輸入，則必須在資料集配置檔案中的後一個轉換之前列出前一個轉換。 否則，Data Workbench伺服器會產生錯誤。 </p> <p> 處理階段提供一種方式，可排序在多個資料集包含檔案中定義的轉換。 對於所有資料集，包括與特定處理階段相關聯的檔案，根據其輸入和輸出對轉換進行排序。 此外，如果多個資料集在轉換後，將檔案輸出至相同欄位，Data Workbench伺服器便會產生錯誤。 </p> <p> 有關階段的詳細資訊，請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">日誌處理配置檔案</a>、<a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md">轉換配置檔案</a>和<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md">資料集包含檔案</a>。 </p> <p><span class="wintitle">轉換相依圖</span>可顯示如何通過一系列轉換修改欄位。 請參閱<a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md">資料集組態工具</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出名稱 </td> 
   <td colname="col2"> 大多數轉換都指定一個輸出欄位。 如果輸出是用戶定義的擴展欄位，則此欄位的名稱必須以"x-"開頭。 輸出欄位名稱不能包含空格或特殊字元。 擴充欄位的名稱可混用大小寫寫寫成，例如"x-NewCampaignName"或"x-New-Campaign-Name"以利閱讀，但軟體會將其視為不區分大小寫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入欄位 </td> 
   <td colname="col2"> <p>輸入欄位是指一個基線欄位，或由先前轉換的輸出產生的用戶建立欄位。 如果需要常數字串，可以使用引號字串，而不是基線或用戶建立的欄位。 </p> <p> 如需Data Workbench伺服器可處理之部分常定義資料欄位的清單，請參閱<a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md">事件資料記錄欄位</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 簡單字串和字串向量 </td> 
   <td colname="col2"> 所有轉換都對字串和/或字串的向量進行操作。 簡單字串是字元的常值序列。 字串向量以特定順序包含零個或更簡單的字串。 </td> 
  </tr> 
 </tbody> 
</table>
