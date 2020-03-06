---
description: 建立子集時，必須指定級別。
solution: Analytics
title: 選擇層
topic: Data workbench
uuid: 18c2bee7-a70f-4510-978f-830b56780f47
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 選擇層{#select-a-level}

建立子集時，必須指定級別。

層級是任何可計數的維度。 例如，如果您正在處理網站資料，如果您從「週日」維度選取元素「Tue」並建立子集，則必須選取您要檢視的層級：頁面檢視、作業或訪客。

* **周中的某天=&quot;Tue&quot;（依頁面檢視）:** 頁面檢視層級僅顯示星期二發生的頁面檢視。

   ![](assets/vis_Subset_byPageView.png)

* **星期幾=&quot;星期二&quot;（依工作階段）:** 會話級別僅顯示在星期二發生的會話。

   ![](assets/vis_Subset_bySession.png)

* **星期幾=&quot;星期二&quot;，由訪客列出：** 訪客層級會顯示星期二瀏覽網站的所有訪客，但也會顯示其他日期的相同訪客造訪網站。

   ![](assets/vis_Subset_byVisitor.png)

