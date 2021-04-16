---
description: 階層檢視僅在使用網站或應用程式時HBX才可用。
title: 套用階層檢視
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# 套用階層檢視{#apply-hierarchy-views}

階層檢視僅在使用網站或應用程式時HBX才可用。

階層檢視會依檔案名稱以階層式方式組織網站中的頁面，並依字母順序排序。 階層檢視雖然對分析本身有用，但也可用來設定進階視覺化，如流程地圖。 有關進程映射的詳細資訊，請參閱[進程映射](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e)。

>[!NOTE]
>
>如果您的資料集已設定為可在叢集中的多部伺服器上執行，為使此功能正常運作，系統管理員必須指定哪些機器可當成中央標準化伺服器。 有關執行此操作的步驟，請參閱&#x200B;*資料集配置指南*&#x200B;中的日誌處理配置檔案一章。

![](assets/vis_Table_CompareHierarchy.png)

**若要啟用或停用階層檢視**

* 在任何頁面或URI視覺化中，以滑鼠右鍵按一下元素或頁面維度標籤，然後按一下&#x200B;**[!UICONTROL Hierarchy View]**。

   ![](assets/mnu_Table_HierarchyView.png)

   當[!DNL hierarchy view]處於活動狀態時，選項旁會顯示X。

   階層會使用樹狀結構，組織成網站區段和頁面。 可使用節名稱旁的+或——符號來展開或壓縮節（節點）。 個別頁面旁沒有+或——符號。

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## 在層次視圖中遮色Dimension元素{#section-e477c469934846da8d807f92fc2f3ed1}

遮色片是指選取維度中資料的子集或元素的子集。 您可遮色或隱藏不想要包含在分析中的元素。 使用階層檢視的[!DNL Mask]功能表選項，您可以選取元素必須顯示在視覺化中之量度的最小百分比。

**要使用菜單選項遮 [!DNL Mask] 罩資料**

1. 按一下右鍵某個元素或維的標籤，然後按一下&#x200B;**[!UICONTROL Mask]**。

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. 在「多於」下方，按一下適當的百分比，然後按一下您要遮色的量度。

例如，如果您按一下0.1%，然後按一下「頁面檢視」，您會遮色（隱藏）任何頁面檢視總數少於0.1%的元素，並顯示頁面檢視總數超過0.1%的任何元素。 如果按一下0%，您會為選取的量度遮色0（零）的所有元素。
