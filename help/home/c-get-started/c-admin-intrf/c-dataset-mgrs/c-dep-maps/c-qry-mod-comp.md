---
description: 關於查詢模型元件的概念性資訊。
solution: Analytics
title: 查詢模型元件
topic: Data workbench
uuid: 708fab0b-dc10-4306-b410-49268069ac3b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查詢模型元件{#query-model-components}

關於查詢模型元件的概念性資訊。

下圖顯示相依關係圖，其節點代表查詢模型的量度、衍生維度和篩選器，這些量度和篩選器在描述檔中的「維度」、「量度」和「篩選器」資料夾中定義，以及資料集中以某種方式定義的延伸維度。

![](assets/vis_DependencyMap_QueryModel.png)

* 黃色——綠色節點代表濾鏡。
* 紫色節點代表度量。
* 藍綠節點表示派生的維。
* 綠色節點表示擴展維（在資料集中定義）。
* 紅色節點表示量度、衍生維度或篩選，其依賴關係或其他錯誤已中斷或循環。

>[!NOTE]
>
>由於相關性映射的設計是為了適應非循環相關性，因此循環相關性中涉及的節點可能無法在映射上正確顯示。 通過在文本框中鍵入「循環相關性」，可以搜索循環相 [!DNL Search] 關性。 如需功能的詳細資 [!DNL Search] 訊，請參 [閱「在地圖內搜尋」](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)。

