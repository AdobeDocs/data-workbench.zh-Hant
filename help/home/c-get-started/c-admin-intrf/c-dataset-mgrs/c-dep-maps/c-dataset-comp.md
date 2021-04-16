---
description: 資料集元件的概念性資訊。
title: 資料集元件
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# 資料集元件{#dataset-components}

資料集元件的概念性資訊。

下圖顯示相依性映射，其節點代表資料集的記錄來源、欄位、轉換和延伸維度。

![](assets/vis_DependencyMap.png)

* 黃色——綠色節點代表資料集中定義的一或多個記錄來源或篩選器（例如記錄項目條件）。

   * 日誌源的節點始終位於映射中最左側。 如果您的資料集有單一記錄來源，地圖會顯示記錄來源：*日誌源名稱*。 如果您的資料集有多個記錄來源，地圖會顯示&#x200B;*number*&#x200B;記錄來源，其中number是記錄來源的計數。 例如，如果您的資料集中有三個記錄檔來源，您的地圖會顯示3個記錄檔來源。

   * 映射為每個[!DNL log processing dataset include]檔案顯示一個「日誌條目條件」節點，但只顯示一個用於轉換的「日誌條目條件」節點（如果在[!DNL Transformation.cfg]檔案中定義）。 如果「記錄項目條件」為空，則不會顯示在地圖上。

* 灰色節點表示列在[!DNL Log Processing.cfg]或[!DNL Log Processing include]檔案中「欄位」參數中的欄位。

* 藍色節點表示轉換。
* 綠色節點表示擴展維。

>[!NOTE]
>
>如果您描述檔的「資料集」檔案夾包含檔案[!DNL Insight Transform.cfg]，相依性對應會顯示為搭配「轉換」使用而定義的記錄檔來源、轉換和匯出器。 有關轉換的資訊，請參見&#x200B;*資料集配置指南*。

啟用「包含[!DNL File Blocks]顯示」選項後，映射將顯示一個藍色節點用於一個資料集配置檔案中定義的所有轉換，而一個綠色節點用於一個資料集配置檔案中定義的所有擴展維。 有關此顯示選項的詳細資訊，請參閱[使用檔案塊](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc)。
