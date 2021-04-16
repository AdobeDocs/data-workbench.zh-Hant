---
description: 有關工作區和視覺化的概念性資訊。
title: 工作區和視覺效果
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# 工作區和視覺效果{#workspaces-and-visualizations}

有關工作區和視覺化的概念性資訊。

下圖顯示了一個相依關係圖，其節點表示配置檔案中定義的工作區、報告、菜單選項和全局層。 此選項僅在[!DNL Query Model]顯示選項啟用時有效。

>[!NOTE]
>
>如果您選擇[!DNL Workspaces and Visualizations]顯示選項時未啟用[!DNL Query Model]顯示選項，則會出現錯誤訊息。

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* 灰色節點代表工作區或報表。
* 黃色——綠色節點表示菜單選項。
* 紅色節點表示工作區、報告、菜單選項或全局層，其中存在中斷或循環相關性或其它錯誤。

>[!NOTE]
>
>由於相關性映射的設計是為了適應非循環相關性，因此循環相關性中涉及的節點可能無法在映射上正確顯示。 通過在[!DNL Search]文本框中鍵入&quot;circular dependency&quot;，可以搜索循環依賴項。 有關[!DNL Search]功能的詳細資訊，請參閱[在映射中搜索](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb)。

有關映射上其他節點的說明，請參閱[查詢模型元件](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f)。
