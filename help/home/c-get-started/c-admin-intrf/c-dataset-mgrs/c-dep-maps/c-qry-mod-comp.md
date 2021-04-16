---
description: 關於查詢模型元件的概念性資訊。
title: 查詢模型元件
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
exl-id: 1f5d0a3a-6647-4762-ab20-9d80e467d48f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 3%

---

# 查詢模型元件{#query-model-components}

關於查詢模型元件的概念性資訊。

下圖顯示相依關係圖，其節點代表查詢模型的量度、衍生維度和篩選器，這些量度和篩選器定義於描述檔中的Dimension、量度和篩選器資料夾，以及資料集中定義的延伸維度（以某種方式與它們相關）。

![](assets/vis_DependencyMap_QueryModel.png)

* 黃色——綠色節點代表濾鏡。
* 紫色節點代表度量。
* 藍綠節點表示派生的維。
* 綠色節點表示擴展維（在資料集中定義）。
* 紅色節點表示量度、衍生維度或篩選，其依賴關係或其他錯誤已中斷或循環。

>[!NOTE]
>
>由於相關性映射的設計是為了適應非循環相關性，因此循環相關性中涉及的節點可能無法在映射上正確顯示。 通過在[!DNL Search]文本框中鍵入&quot;circular dependency&quot;，可以搜索循環依賴項。 有關[!DNL Search]功能的詳細資訊，請參閱[在映射中搜索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)。
