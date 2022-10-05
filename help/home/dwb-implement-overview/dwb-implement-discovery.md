---
description: 收集並說明實作Data Workbench時適合您行銷環境的業務問題。
title: Data Workbench 探索與需求
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
exl-id: 25cc2940-800a-4ad2-a7bb-c343e3d65500
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 8%

---

# Data Workbench 探索與需求{#data-workbench-discovery-and-requirements}

{{eol}}

收集並說明實作Data Workbench時適合您行銷環境的業務問題。

本節可讓您收集關於在Data Workbench(DWB)中設計解決方案所需問題和任務的投入，以便準確、明確、且以獨立於技術的方式處理這些問題，提供業務術語和Adobe Analytics Premium解決方案的參考。 本節提供這些目標和相關要求的資訊。

## 階段1:主要業務目標/目標 {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

下表提示您識別客戶群，並分析DWB實作的建構。

* 了解您的客戶群
* 了解特定業務案例（例如自助服務和其他資料管道/離線資料來源的成效）

**了解您的客戶群**

了解客戶為何使用您的網站、您面臨的挑戰，以及DWB如何根據您的業務模式為您提供協助。 例如，如何測量、監控和分析您的客戶，以交叉銷售其他產品和服務、取得活躍使用者清單和帳戶滲透率，以及其他目標。

| ID | 業務問題/需求 | 優先順序 | 階段 | 相依性 |
|---|---|---|---|---|
| 1a | 特定業務問題1 | 高/中/低 | 1 | 共同金鑰，取決於其他金鑰等。 |
| 1b | 特定業務問題2 | 高 | 1 | 任何相依性 |

分析建構

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace Analysis資料來源</td> 
   <td colname="col2"> 新增工作區名稱 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>需要的工作區Dimension和量度 </p> </td> 
   <td colname="col2"> <p>識別Dimension: </p> <p>識別量度： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 需要的工作區篩選器、標幟和工具 </td> 
   <td colname="col2"> <p>識別區段： </p> <p>識別工具： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 此分析可衍生哪些動作？ </td> 
   <td colname="col2"> 使用特定DWB工作區來了解工作和內容。 </td> 
  </tr> 
 </tbody> 
</table>

## 階段2:了解特定業務案例 {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

了解其他資料來源和管道，並了解這些與您的業務案例有何關係。

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 業務問題/需求 </th> 
   <th colname="col3" class="entry"> 優先順序 </th> 
   <th colname="col04" class="entry"> 階段 </th> 
   <th colname="col4" class="entry"> 相依性 </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> 特定業務要求1 </td> 
   <td colname="col3"> <p>高/中/低 </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>共同金鑰，取決於其他金鑰、帳戶標幟/識別碼等 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>特定業務要求2 </p> </td> 
   <td colname="col3"> 高/中/低 </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>任何相依性 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**分析構造**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Workspace Analysis資料來源
     </td> 
   <td colname="col2">
     工作區名稱範例 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>需要的工作區Dimension和量度 </p> </td> 
   <td colname="col2"> <p>Dimension:定義所需的維度。 </p> <p>量度：定義所需的量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 需要的工作區篩選器、標幟和工具 </td> 
   <td colname="col2"> <p>區段：識別客戶區段。 </p> <p>工具：選擇所需工具。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 此分析可衍生哪些動作？ </td> 
   <td colname="col2"> 從此工作區了解什麼 </td> 
  </tr> 
 </tbody> 
</table>

**資料來源**

| 資料來源 | 優先順序 | 資料的接收頻率為何？ |
|---|---|---|
| 網站1名稱報表套裝(RSID) | 1 | 每小時 |
| 網站2名稱（若有）(RSID) | 1 | 每小時 |
| 資料來源1（若適用） | 2 | 每日? |
| 資料來源2（若適用） | 3 | 每日? |
