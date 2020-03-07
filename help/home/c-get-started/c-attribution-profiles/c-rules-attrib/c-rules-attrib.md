---
description: 使用資料工作台中以規則為基礎的新歸因設定檔，您可以快速分析歸因事件並指派責任，以促成您定義的成功轉換。 Attribution描述檔隨附資料架構師設定和擴充其功能所需的資訊，並包含預先建立的工作區，讓分析人員可立即開始分析。
solution: Analytics
title: 歸因設定檔
topic: Data workbench
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Attribution Profile{#attribution-profile}

使用資料工作台中以規則為基礎的新歸因設定檔，您可以快速分析歸因事件並指派責任，以促成您定義的成功轉換。 Attribution描述檔隨附資料架構師設定和擴充其功能所需的資訊，並包含預先建立的工作區，讓分析人員可立即開始分析。

「歸因」設定檔可讓您從新的角度瞭解行銷成果與成功的客戶潛在客戶開發或銷售轉化之間的關係。 「歸因」設定檔可協助您限定互動，這些互動應接收分配的評分，以獲得實現的收入或下遊客戶體驗的參與。 它可協助您快速分析歸因事件，然後指派第一次或最後一次接觸或其他導致成功銷售的事件的責任，以識別行銷工作和成本的影響。

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>「歸因」描述檔已設定為讓已實作使用Analytics(SC/Insight)資料饋送之Adobe SC描述檔的使用者立即使用。 依預設，「行銷」和「轉換」事件會作為預設類型的互動，在提供的規則型模型中評估。

如需 [其他資訊，請參閱](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) 「部 [署歸因設定檔和歸因模型](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) 」。

## 架構和分析工作區 {#section-27c6aff70ba147cca6e11451e127afb4}

在「歸因」描述檔中，您在工作台的個別標籤上定義了「架構設計人員」和「分析師」工作區。

![](assets/attribution_profile_tabs.png)

**架構工作區**

在「歸 **因** 」索引標籤中，按一 **[!UICONTROL Architect Workspace]** 下索引標籤以開啟專為設定基本歸因模型之組態檔案而設計的工作區。

![](assets/attribution_profile_arch.png)

「體系結構」(Architecture)頁籤包括工作區，用於逐步執行配置檔案資料集資料夾中的每個配置檔案。 例如，可 **[!UICONTROL Attribution Configuration - Step 1]** 讓您在檔案的「轉換」區段中識別「歸因」 [!DNL profile.cfg] 值。

![](assets/attribution_profile_arch_step1.png)

**分析工作區** —按一下 **[!UICONTROL Analyst]** 「索引標籤」，以開 **[!UICONTROL Workspaces]** 啟使用歸因設定檔隨附的維度和度量的預先建立工作區分析。

這些工作區分為四類：

1. **「基本報表** 」會在工作區中公開單一模型。
1. **比較報表** (Compartion Reports)在單一檢視中呈現多個模型，以延伸分析。
1. **「調查報表** 」會展開報表範本，以不同格式呈現歸因模型。 本節還介紹並公開了基於位置的加權比。
1. **路徑報表** (Pathing Reports)提供多個路徑視覺化，可洞察客戶的行銷歷程，以全面探索並表達流程和互動路徑

![](assets/attribution_profile_analyst.png)

「分析師」標籤包含預先設定好報表的工作區。 例如，可 **[!UICONTROL First Attribution]** 讓您從表格中選 **[!UICONTROL Campaign]** 擇，以檢視 **[!UICONTROL Revenue]** 根據的歸因 **[!UICONTROL Time]**。

![](assets/attribution_profile_analyst_step1.png)

