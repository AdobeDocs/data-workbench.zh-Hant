---
description: 在工作區中，視覺化代表一組查詢結果。
title: 瞭解選取項目對其他視覺效果的影響
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# 瞭解選取項目對其他視覺效果的影響{#understanding-how-a-selection-affects-other-visualizations}

在工作區中，視覺化代表一組查詢結果。

當您進行選取時，Data Workbench會篩選查詢的結果，以便在工作區中產生視覺化。 特定篩選條件會依視覺化而有所不同。

下列範例說明Data Workbench如何將選取範圍套用至三種不同的視覺化類型。 檢閱這些範例可協助您瞭解選取範圍對視覺化的篩選效果。 它們也可協助您瞭解如何解讀篩選視覺化中的結果。

* [使用工作階段度量篩選視覺化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [使用訪客度量篩選視覺化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [使用逐個作業的訪客度量篩選視覺化](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## 使用作業度量{#section-7cc06493ecb34cd4a696dbf0f0a7aaef}篩選視覺化

在此範例中，左側視覺化中的[!DNL /direct.asp/?ldPage=hme] URI會篩選右側視覺化中顯示之「工作階段」度量。

![](assets/client-vis1.png)

* **「選擇」對「查詢：** Data Workbench」的影響會過濾選定URI的會話。在此示例中，將按如下方式篩選生成[!DNL /pops/disclosure_pop.asp]元素值的查詢：

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **解讀視覺化：** 篩選的視覺化表示包含視覺化和中所列URI的作業數 [!DNL /direct.asp/?ldPage=hme]。此範例顯示有1,113個工作階段，訪客在同一工作階段中檢視了[!DNL /pops/disclosure_pop.asp]頁面和[!DNL /direct.asp/?ldPage=hme]。

## 使用訪客度量{#section-97d38c7f03e8457189a9c72d69514ed2}篩選視覺化

在此範例中，左側視覺化中的[!DNL /direct.asp/?ldPage=home] URI會篩選右側視覺化中訪客的量度。

![](assets/client-vis2.png)

* **「選擇」對「查詢：** Data Workbench」的影響會篩選所選URI的訪客。在此示例中，生成[!DNL /pops/disclosure_pop.asp] URI值的查詢按如下方式進行篩選：

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **解讀視覺化：** 篩選的視覺化會描述已檢視視覺化中所列URI的訪客， [!DNL /direct.asp/?ldPage=hme] 但不一定在同一作業中檢視過。上述範例顯示有2,041位訪客同時檢視了[!DNL /pops/disclosure_pop.asp]和[!DNL /direct.asp/?ldPage=hme]。

## 使用逐個作業的訪客度量篩選視覺化{#section-f746182311d648dcb98716b0fe846e25}

在此範例中，左側視覺化中的[!DNL /direct.asp/?ldPage=hme] URI會在右側視覺化中篩選逐個訪客作業的度量。

![](assets/client-vis3.png)

* **「選擇」對「查詢：** Data Workbench」的影響會依所選URI的作業篩選訪客。例如，生成[!DNL /pops/disclosure_pop.asp] URI值的查詢按如下方式進行篩選：

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **解讀視覺化：篩** 選的視覺化描述了在視覺化中和相同作業期間檢視過兩個URI [!DNL /direct.asp/?ldPage=hme] 的訪客。此範例顯示，1,069位訪客在單一作業期間同時看到[!DNL /pops/disclosure_pop.asp]和[!DNL /direct.asp/?ldPage=hme]。
