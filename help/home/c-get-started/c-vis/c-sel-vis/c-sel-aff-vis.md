---
description: 在工作區中，視覺效果代表一組查詢結果。
title: 瞭解選取項目對其他視覺效果的影響
uuid: d46f4e8d-df6f-4a7f-a796-eb9f11536ae5
exl-id: 7756646b-9309-41aa-a098-8988f6c065c8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 3%

---

# 瞭解選取項目對其他視覺效果的影響{#understanding-how-a-selection-affects-other-visualizations}

在工作區中，視覺效果代表一組查詢結果。

進行選取時，「Data Workbench」會篩選查詢結果，查詢結果將用來在工作區中產生視覺效果。 特定篩選依視覺效果而異。

下列範例說明Data Workbench如何將選取項目套用至三種不同的視覺效果類型。 檢閱這些範例有助於了解選取項目對視覺效果的篩選效果。 它們也可協助您了解如何解讀在篩選視覺效果中看到的結果。

* [使用工作階段量度篩選視覺效果](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-7cc06493ecb34cd4a696dbf0f0a7aaef)
* [使用訪客量度篩選視覺效果](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-97d38c7f03e8457189a9c72d69514ed2)
* [使用依工作階段的訪客量度篩選視覺效果](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-aff-vis.md#section-f746182311d648dcb98716b0fe846e25)

## 使用工作階段量度{#section-7cc06493ecb34cd4a696dbf0f0a7aaef}篩選視覺效果

在此範例中，左側視覺效果中的[!DNL /direct.asp/?ldPage=hme] URI會篩選右側視覺效果中顯示的工作階段量度。

![](assets/client-vis1.png)

* **選擇對查詢的影響：** Data Workbench會篩選所選URI的會話。在此示例中，生成[!DNL /pops/disclosure_pop.asp]元素值的查詢按如下方式篩選：

   ```
   Sessions[ URI="/pops/disclosure_pop.asp" AND URI="/direct.asp
   /?ldPage=hme"] by Page View by Session
   ```

* **解譯視覺效果：** 篩選的視覺效果代表包含列在視覺效果和中之URI的工作階段 [!DNL /direct.asp/?ldPage=hme]數。此範例顯示有1,113個工作階段，訪客在其中檢視了相同工作階段中的[!DNL /pops/disclosure_pop.asp]頁面和[!DNL /direct.asp/?ldPage=hme]。

## 使用訪客量度{#section-97d38c7f03e8457189a9c72d69514ed2}篩選視覺效果

在此範例中，左側視覺效果中的[!DNL /direct.asp/?ldPage=home] URI是篩選右側視覺效果中訪客的量度。

![](assets/client-vis2.png)

* **選擇對查詢的影響：** Data Workbench會篩選所選URI的訪客。在此示例中，生成[!DNL /pops/disclosure_pop.asp] URI值的查詢按如下方式篩選：

   ```
   Visitors[ URI="/pops/disclosure_pop.asp" by Page View by Visitor 
     AND URI="/direct.asp/?ldPage=hme" by Page View by Visitor ]
   ```

* **解譯視覺效果：** 篩選的視覺效果可描繪已檢視視覺效果和(雖然不一定在同 [!DNL /direct.asp/?ldPage=hme] 一工作階段期間)中所列URI的訪客。上述範例顯示有2,041位訪客同時檢視了[!DNL /pops/disclosure_pop.asp]和[!DNL /direct.asp/?ldPage=hme]。

## 使用每個工作階段的訪客量度{#section-f746182311d648dcb98716b0fe846e25}篩選視覺效果

在此範例中，左側視覺效果的[!DNL /direct.asp/?ldPage=hme] URI是篩選右側視覺效果中依工作階段訪客的量度。

![](assets/client-vis3.png)

* **選取對查詢的影響：** Data Workbench會依工作階段篩選所選URI的訪客。例如，生成[!DNL /pops/disclosure_pop.asp] URI值的查詢按如下方式篩選：

   ```
   Visitors[ ( URI="/pops/disclosure_pop.asp" by Page View 
     AND URI="/direct.asp/?ldPage=hme" by Page View ) by Session ]
   ```

* **解譯視覺效果：** 篩選的視覺效果可描繪在視覺效果中和同一工作階段中，同時檢視了 [!DNL /direct.asp/?ldPage=hme] 兩個URI的訪客。此範例顯示1,069位訪客在單一工作階段期間，同時看到[!DNL /pops/disclosure_pop.asp]和[!DNL /direct.asp/?ldPage=hme]。
