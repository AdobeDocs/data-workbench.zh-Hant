---
description: 階層檢視僅在使用Site或HBX應用程式時才可用。
title: 套用階層檢視
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# 套用階層檢視{#apply-hierarchy-views}

{{eol}}

階層檢視僅在使用Site或HBX應用程式時才可用。

階層檢視會顯示網站中依檔案名稱依階層組織並依字母排序的頁面。 階層檢視雖然對分析本身很有用，但也可用來設定程式圖之類的進階視覺效果。 如需程式圖的詳細資訊，請參閱 [程式圖](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>如果資料集已配置為在一個群集中的多個伺服器上運行，為了使此功能正常工作，系統管理員必須指定哪台電腦可以用作中央標準化伺服器。 如需執行此動作的步驟，請參閱 *資料集組態指南*.

![](assets/vis_Table_CompareHierarchy.png)

**啟用或禁用層次結構視圖**

* 在任何頁面或URI視覺效果中，以滑鼠右鍵按一下元素或頁面維度的標籤，然後按一下 **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   當 [!DNL hierarchy view] 活動。

   階層會使用樹狀結構來組織為網站區段和頁面。 可使用節名稱旁的+或 — 符號來展開或縮減節（節點）。 個別頁面旁沒有+或 — 符號。

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## 遮罩層次視圖中的Dimension元素 {#section-e477c469934846da8d807f92fc2f3ed1}

遮罩是指選取資料的子集或維度中元素的子集。 您可以遮罩或隱藏不想包含在分析中的元素。 使用 [!DNL Mask] 的功能表選項，您可以選取元素必須顯示在視覺效果中之量度的最小百分比。

**若要使用來遮罩資料 [!DNL Mask] 選單選項**

1. 以滑鼠右鍵按一下維度的元素或標籤，然後按一下 **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. 在「多於」下，按一下適當的百分比，然後按一下您要遮罩的量度。

例如，如果您按一下0.1%，然後按一下「頁面檢視」，您就會遮罩（隱藏）任何頁面檢視總數少於0.1%的元素，並顯示任何頁面檢視總數超過0.1%的元素。 如果按一下0%，則會為所選度量遮罩值為0（零）的所有元素。
