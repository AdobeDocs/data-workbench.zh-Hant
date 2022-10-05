---
description: 關於工作區和視覺效果的概念資訊。
title: 工作區和視覺效果
uuid: dc7fab6c-d8b4-4ed7-bad6-b3df14b9ebbf
exl-id: a70748dd-8190-4d1b-9ee1-1011b73a1a86
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# 工作區和視覺效果{#workspaces-and-visualizations}

{{eol}}

關於工作區和視覺效果的概念資訊。

下圖顯示了一個相依圖，其節點表示配置檔案中定義的工作區、報告、菜單選項和全局層。 只有在 [!DNL Query Model] 顯示選項。

>[!NOTE]
>
>若 [!DNL Query Model] 當您選擇 [!DNL Workspaces and Visualizations] 顯示選項時，會顯示錯誤訊息。

![](assets/vis_DependencyMap_QueryModelandWorkspaces.png)

* 灰色節點代表工作區或報表。
* 黃色 — 綠色節點代表功能表選項。
* 紅色節點表示工作區、報表、菜單選項或全局層，其中存在中斷或循環依賴關係或其他錯誤。

>[!NOTE]
>
>由於依賴關係映射的設計是為了適應無環依賴關係，因此循環依賴關係中涉及的節點可能無法在映射上正確顯示。 您可以在 [!DNL Search] 框。 如需 [!DNL Search] 功能，請參閱 [在地圖中搜尋](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/t-srch-map.md#task-a1e7065a538d46c78a7d28676d880dfb).

如需地圖上其他節點的說明，請參閱 [查詢模型元件](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-qry-mod-comp.md#concept-32c6dadd32f74179b026c7e96d47710f).
