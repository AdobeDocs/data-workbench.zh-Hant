---
description: 在「Data Workbench」中使用新的規則型歸因設定檔，您可以快速分析歸因事件，並指派導致您所定義之成功轉換的責任。 歸因設定檔隨附設定和擴充功能所需的資訊，並包含預先建立的工作區，供分析人員直接進入並開始分析。
title: 歸因設定檔
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# 歸因設定檔{#attribution-profile}

{{eol}}

在「Data Workbench」中使用新的規則型歸因設定檔，您可以快速分析歸因事件，並指派導致您所定義之成功轉換的責任。 歸因設定檔隨附設定和擴充功能所需的資訊，並包含預先建立的工作區，供分析人員直接進入並開始分析。

歸因設定檔可讓您從新的角度了解行銷工作與成功的客戶銷售機會產生或銷售轉換之間的關係。 歸因設定檔可協助您讓互動合格，這些互動應接收已實現收入或下游參與客戶歷程的評分分配。 它可讓您快速分析歸因事件，然後指派對首次接觸或最後接觸或其他事件的責任，進而協助您識別行銷工作和成本的影響，進而促成成功的銷售。

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>歸因設定檔已設定為讓已實作使用Analytics(SC/Insight)資料摘要的AdobeSC設定檔的使用者立即使用。 依預設，行銷和轉換事件會作為提供之規則型模型中評估的預設互動類型。

請參閱 [部署歸因設定檔](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) 和 [歸因模型](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) 以取得其他資訊。

## 架構和分析工作區 {#section-27c6aff70ba147cca6e11451e127afb4}

在歸因設定檔中，您的架構師和分析師工作區會定義於工作台的個別標籤上。

![](assets/attribution_profile_tabs.png)

**架構工作區**

在 **歸因** ，按一下 **[!UICONTROL Architect Workspace]** 標籤來開啟專為設定基本歸因模型組態檔而設計的工作區。

![](assets/attribution_profile_arch.png)

「架構」索引標籤包含可逐步執行設定檔資料集資料夾中每個設定檔案的工作區。 例如， **[!UICONTROL Attribution Configuration - Step 1]** 可讓您識別 [!DNL profile.cfg] 檔案。

![](assets/attribution_profile_arch_step1.png)

**分析人員工作區** 按一下 **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** 索引標籤，使用歸因設定檔隨附的維度和量度，開啟預先建立的工作區分析。

這些工作區分為四類：

1. **基本報表** 在工作區中公開單一模型。
1. **比較報表** 在單一檢視中顯示多個模型，以擴展分析。
1. **調查報告** 展開報表範本，以不同格式呈現歸因模型。 本節還介紹並公開基於位置的加權比率。
1. **路徑報表** 透過多個路徑視覺效果提供客戶行銷歷程的可見度，以充分探索及表達流程和互動路徑

![](assets/attribution_profile_analyst.png)

「分析師」索引標籤包含已預先設定報表的工作區。 例如， **[!UICONTROL First Attribution]** 可讓您從 **[!UICONTROL Campaign]** 表格以檢視 **[!UICONTROL Revenue]** 歸因根據 **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)
