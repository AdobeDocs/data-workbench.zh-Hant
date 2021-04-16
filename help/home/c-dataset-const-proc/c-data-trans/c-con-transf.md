---
description: 表格顯示在構建轉換時應用的約定。
title: 建構轉換的慣例
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
exl-id: c2552c52-c6d3-4c9f-8359-b5a58bf1a59f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 2%

---

# 建構轉換的慣例{#conventions-for-constructing-transformations}

表格顯示在構建轉換時應用的約定。

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
   <td colname="col2"> <p>資料集配置檔案中的轉換按順序應用於日誌條目（即，按照它們在配置檔案中的列出順序）。 因此，必須按其輸出用作其他轉換的輸入順序列出轉換。 更具體地說，如果將一個轉換的輸出用作另一個轉換的輸入，則在資料集配置檔案中的後一個轉換之前列出前一個轉換非常重要。 否則，資料工作台伺服器會生成錯誤。 </p> <p> 處理階段提供一種方式，來排序在多個資料集中定義的轉換包括檔案。 對於所有資料集包括與特定處理階段相關聯的檔案，根據其輸入和輸出對變換進行排序。 此外，如果多個資料集包含舞台內的檔案輸出資料到與轉換結果相同的欄位，則資料工作台伺服器生成錯誤。 </p> <p> 有關階段的詳細資訊，請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">日誌處理配置檔案</a>、<a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md">轉換配置檔案</a>和<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md">資料集包含檔案</a>。 </p> <p><span class="wintitle">轉換相關性圖</span>可顯示如何通過一系列轉換修改欄位。 請參閱<a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md">資料集設定工具</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出名稱 </td> 
   <td colname="col2"> 大多數轉換都指定輸出欄位。 如果輸出是用戶定義的擴展欄位，則此欄位的名稱必須以"x-"開頭。 輸出欄位名稱不能包含空格或特殊字元。 擴充欄位的名稱可以混合使用大小寫，例如「x-NewCampaignName」或「x-New-Campaign-Name」，以利閱讀，但軟體會將這些欄位視為不區分大小寫。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入欄位 </td> 
   <td colname="col2"> <p>輸入欄位是指其中一個基線欄位或由先前轉換輸出生成的用戶建立的欄位。 如果需要常數字串，可以使用引號字串來取代基線或使用者建立的欄位。 </p> <p> 如需資料工作台伺服器可處理的部分常定義資料欄位清單，請參閱<a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md">事件資料記錄欄位</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 簡單字串和字串向量 </td> 
   <td colname="col2"> 所有轉換都對字串和／或字串向量運作。 簡單字串是字元的常值序列。 字串向量以特定順序包含零個或更簡單的字串。 </td> 
  </tr> 
 </tbody> 
</table>
