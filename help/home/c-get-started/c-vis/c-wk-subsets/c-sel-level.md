---
description: 建立子集時，必須指定級別。
title: 選取層級
uuid: 18c2bee7-a70f-4510-978f-830b56780f47
exl-id: 39d8407c-e2ec-4080-8918-26cafbf988df
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---

# 選取層級{#select-a-level}

{{eol}}

建立子集時，必須指定級別。

層級是任何可數維度。 例如，若您正在處理網站資料，如果從「星期」維度選取元素「週二」並建立子集，則必須選取您要檢視的層級：頁面檢視、工作階段或訪客。

* **依頁面檢視，星期=&quot;星期二&quot;:** 頁面檢視層級只會顯示星期二發生的頁面檢視。

   ![](assets/vis_Subset_byPageView.png)

* **星期=&quot;星期二&quot;（按會話）:** 工作階段層級只會顯示星期二發生的工作階段。

   ![](assets/vis_Subset_bySession.png)

* **按訪客列出的星期=&quot;星期二&quot;:** 訪客層級會顯示每星期二來到網站的所有訪客，但也會顯示其他日期相同的訪客造訪網站。

   ![](assets/vis_Subset_byVisitor.png)
