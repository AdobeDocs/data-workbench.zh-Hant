---
description: 「促銷活動」維度是在「網站行銷」設定檔中定義，以提供促銷活動分析功能。
title: 行銷設定檔維度
uuid: 034b4318-58e6-4638-9b13-fac83ff9f826
exl-id: 93804fba-a44b-4cdc-8d67-d4ec0656e742
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 5%

---

# 行銷設定檔維度{#marketing-profile-dimensions}

{{eol}}

「促銷活動」維度是在「網站行銷」設定檔中定義，以提供促銷活動分析功能。

<table id="table_27A4B8247F6D4E18BD61041CED7D8805"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 維度 </th> 
   <th colname="col2" class="entry"> 類型 </th> 
   <th colname="col3" class="entry"> 層級 </th> 
   <th colname="col4" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 促銷活動 </td> 
   <td colname="col2"> 重新命名為簡單 </td> 
   <td colname="col3">工作階段 <p>第一行操作 </p></td> 
   <td colname="col4"> 從訪客第一個請求中的值擷取的促銷活動識別碼。 </td> 
  </tr> 
 </tbody> 
</table>

**自訂行銷設定檔Dimension範例**

您可以合併其他資料維度以供進一步分析。 通過將附加資訊併入為分析而收集的資料流來添加這些維度。 例如，下表包含一些已新增至部署中的自訂行銷維度，供各行業的客戶使用：

| Dimension（自訂） | 說明 |
|---|---|
| 電子郵件促銷活動日期 | 從電子郵件促銷活動查詢字串分析促銷活動日期（第一個值）。 |
| 電子郵件促銷活動詳細資料 | 收集附加至電子郵件促銷活動查詢字串變數的值字串。 |
| 電子郵件促銷活動區段 | 從電子郵件促銷活動查詢字串分析促銷活動區段（第三個值）。 |
| 電子郵件促銷活動類型 | 從電子郵件促銷活動查詢字串分析促銷活動類型（第二個值）。 |
| 行銷活動詳細資料 | 收集附加至行銷活動查詢字串變數的值字串。 |
| 行銷活動擁有者 | 從行銷活動查詢字串剖析行銷活動擁有者（第四個值）。 |
| 行銷活動來源 | 從行銷活動查詢字串分析促銷活動來源（第一個值）。 |
| 行銷活動類型 | 從行銷活動查詢字串分析促銷活動類型（第二個值）。 |
| PPC促銷活動詳細資訊 | 收集附加至ppc查詢字串變數的值字串。 |
