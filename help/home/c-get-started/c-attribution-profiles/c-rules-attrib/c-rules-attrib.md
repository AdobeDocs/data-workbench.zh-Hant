---
description: 使用Data Workbench中以規則為基礎的新歸因設定檔，您可以快速分析歸因事件並指派責任，以促成您定義的成功轉換。 Attribution描述檔隨附資料架構師設定和擴充其功能所需的資訊，並包含預先建立的工作區，讓分析人員可立即開始分析。
title: 歸因設定檔
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# 歸因設定檔{#attribution-profile}

使用Data Workbench中以規則為基礎的新歸因設定檔，您可以快速分析歸因事件並指派責任，以促成您定義的成功轉換。 Attribution描述檔隨附資料架構師設定和擴充其功能所需的資訊，並包含預先建立的工作區，讓分析人員可立即開始分析。

「歸因」設定檔可讓您從新的角度瞭解行銷成果與成功的客戶潛在客戶開發或銷售轉化之間的關係。 「歸因」設定檔可協助您限定互動，這些互動應接收分配的評分，以獲得實現的收入或下遊客戶體驗的參與。 它可協助您快速分析歸因事件，然後指派第一次或最後一次接觸或其他導致成功銷售的事件的責任，以識別行銷工作和成本的影響。

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>「歸因」描述檔已設定為讓已實作使用Analytics(SC/Insight)資料饋送之AdobeSC描述檔的使用者立即使用。 依預設，「行銷」和「轉換」事件會作為預設類型的互動，在提供的規則型模型中評估。

如需詳細資訊，請參閱[部署歸因設定檔](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0)和[歸因模型](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d)。

## 架構和分析工作區{#section-27c6aff70ba147cca6e11451e127afb4}

在「歸因」描述檔中，您在工作台的個別標籤上定義了「架構設計人員」和「分析師」工作區。

![](assets/attribution_profile_tabs.png)

**架構工作區**

在&#x200B;**Attribution**&#x200B;標籤中，按一下&#x200B;**[!UICONTROL Architect Workspace]**&#x200B;標籤，以開啟專為設定基本歸因模型之組態檔案而設計的工作區。

![](assets/attribution_profile_arch.png)

「體系結構」(Architecture)頁籤包括工作區，用於逐步執行配置檔案資料集資料夾中的每個配置檔案。 例如，**[!UICONTROL Attribution Configuration - Step 1]**&#x200B;可讓您在[!DNL profile.cfg]檔案的「轉換」區段中識別「歸因」值。

![](assets/attribution_profile_arch_step1.png)

**分析工** 作區：按一 **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** 下標籤，使用歸因設定檔所提供的維度和量度開啟預先建立的工作區分析。

這些工作區分為四類：

1. **基本** 報表在工作區中建立單一模型。
1. **比較** 報告在單一觀點內呈現多種模型，以擴展分析。
1. **調查** 報告會擴充報告範本，以不同格式呈現歸因模型。本節還介紹並公開了基於位置的加權比。
1. **路徑** 報表透過多個路徑視覺化功能，提供客戶行銷歷程的可見度，以全面探索並表達流程流程和互動路徑

![](assets/attribution_profile_analyst.png)

「分析師」標籤包含預先設定好報表的工作區。 例如，**[!UICONTROL First Attribution]**&#x200B;可讓您從&#x200B;**[!UICONTROL Campaign]**&#x200B;表格中選取，以檢視基於&#x200B;**[!UICONTROL Time]**&#x200B;的&#x200B;**[!UICONTROL Revenue]**&#x200B;歸因。

![](assets/attribution_profile_analyst_step1.png)
