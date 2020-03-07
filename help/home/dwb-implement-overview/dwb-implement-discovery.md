---
description: 在實施資料工作台時，收集並說明適合您行銷環境的商業問題。
title: 資料工作台探索與需求
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# 資料工作台探索與需求{#data-workbench-discovery-and-requirements}

在實施資料工作台時，收集並說明適合您行銷環境的商業問題。

本節可讓您收集資料工作台(DWB)中設計解決方案所需問題與任務的相關輸入，以精確、明確且不受技術影響的方式解決這些問題，並提供商業術語與Adobe Analytics Premium解決方案的參考。 本節提供有關這些目標和相關要求的資訊。

## 階段1:關鍵業務目標／目標 {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

下表提示您識別客戶群並分析DWB實作的建構。

* 瞭解客戶群
* 瞭解特定業務案例（例如，自助服務和其他資料通道／離線資料來源的成效）

**瞭解您的客戶群**

瞭解客戶使用您網站的原因、您面臨的挑戰，以及DWB如何根據您的業務模式協助您。 例如，如何衡量、監控和分析客戶，以便交叉銷售其他產品和服務、取得有效使用者和帳戶滲透率的清單，以及達成其他目標。

| ID | 業務問題／需求 | 優先順序 | 階段 | 相依性 |
|---|---|---|---|---|
| 1a | 特定業務問題1 | 高／中/低 | 1 | 公共密鑰，取決於某些其他密鑰等。 |
| 1b | 特定業務問題2 | 高 | 1 | 任何相依性 |

分析結構

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">工作區分析資料來源</td> 
   <td colname="col2"> 新增工作區名稱 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>需要的工作區維度與量度 </p> </td> 
   <td colname="col2"> <p>識別維度： </p> <p>識別量度： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 所需的工作區篩選、標幟和工具 </td> 
   <td colname="col2"> <p>識別區段： </p> <p>識別工具： </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 此分析可衍生哪些動作？ </td> 
   <td colname="col2"> 使用特定的DWB工作區來瞭解工作和內容。 </td> 
  </tr> 
 </tbody> 
</table>

## 階段2:瞭解特定業務案例 {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

瞭解其他資料來源和通道，並瞭解這些與您的業務案例有何關聯。

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> 業務問題／需求 </th> 
   <th colname="col3" class="entry"> 優先順序 </th> 
   <th colname="col04" class="entry"> 階段 </th> 
   <th colname="col4" class="entry"> 相依性 </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> 特定業務需求1 </td> 
   <td colname="col3"> <p>高／中/低 </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>公用金鑰，取決於其他金鑰、帳戶標幟／識別碼等。 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>特定業務需求2 </p> </td> 
   <td colname="col3"> 高／中/低 </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>任何相依性 </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**分析結構**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">工作區分析資料來源
     </td> 
   <td colname="col2">
     工作區名稱範例 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>需要的工作區維度與量度 </p> </td> 
   <td colname="col2"> <p>維度：定義所需尺寸。 </p> <p>量度：定義所需的量度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 所需的工作區篩選、標幟和工具 </td> 
   <td colname="col2"> <p>區段：識別客戶細分。 </p> <p>工具：選擇所需工具。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 此分析可衍生哪些動作？ </td> 
   <td colname="col2"> 從此工作區瞭解什麼 </td> 
  </tr> 
 </tbody> 
</table>

**資料來源**

| 資料來源 | 優先順序 | 資料的接收頻率為何？ |
|---|---|---|
| 網站1名稱報表套裝(RSID) | 1 | 每小時 |
| 站點2名稱（如果有）(RSID) | 1 | 每小時 |
| 資料來源1（如果適用） | 2 | 每日? |
| 資料來源2（如果適用） | 3 | 每日? |
