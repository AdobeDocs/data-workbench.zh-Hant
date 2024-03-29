---
description: 資料集元件的概念資訊。
title: 資料集元件
uuid: a5dde039-3b79-4543-9953-995eefc73b5f
exl-id: 6be625c5-1a2e-4b0d-9c34-5f3baec4ba81
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 1%

---

# 資料集元件{#dataset-components}

{{eol}}

資料集元件的概念資訊。

下圖顯示的相依性映射的節點代表資料集的日誌源、欄位、轉換和擴展維。

![](assets/vis_DependencyMap.png)

* 黃色 — 綠色節點代表資料集中定義的一或多個記錄來源或篩選器（例如記錄項目條件）。

   * 日誌源的節點始終位於映射的最左側。 如果您的資料集有單一記錄來源，對應會顯示記錄來源： *日誌源名稱*. 如果您的資料集有多個記錄來源，則會顯示地圖 *數字* 日誌源，其中number是日誌源的計數。 例如，若資料集中有三個記錄來源，您的地圖會顯示3個記錄來源。

   * 地圖會針對每個報表顯示一個記錄項目條件節點 [!DNL log processing dataset include] 檔案，但只有一個用於轉換的日誌條目條件節點(如果在 [!DNL Transformation.cfg] 檔案)。 如果記錄項目條件為空，該條件不會顯示在對應上。

* 灰色節點代表列於 [!DNL Log Processing.cfg] 或 [!DNL Log Processing include] 檔案。

* 藍色節點代表轉換。
* 綠色節點代表延伸維度。

>[!NOTE]
>
>如果設定檔的資料集資料夾包含檔案 [!DNL Insight Transform.cfg]，相依圖會顯示為與轉換搭配使用而定義的記錄來源、轉換和匯出工具。 如需轉換的相關資訊，請參閱 *資料集組態指南*.

啟用「包含」時 [!DNL File Blocks] 顯示選項，地圖會針對一個資料集組態檔中定義的所有轉換顯示單一藍色節點，並針對一個資料集組態檔中定義的所有延伸維度顯示單一綠色節點。 如需此顯示選項的詳細資訊，請參閱 [使用檔案區塊](../../../../../home/c-get-started/c-admin-intrf/c-dataset-mgrs/c-dep-maps/c-wkg-file-blocks.md#concept-3652bbabfbd34449a5f842d8aa598efc).
