---
description: 即使是短期的臨機分析需求，也建議建立控制面板。
title: 建立控制面板
uuid: 5b9e9db2-d7ac-4c97-8df0-74a9e5a0c496
exl-id: bd51d4c0-bcf2-4ba6-8b32-de06c74f359f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 1%

---

# 建立控制面板{#creating-a-dashboard}

{{eol}}

即使是短期的臨機分析需求，也建議建立控制面板。

>[!NOTE]
>
>唯讀使用者無法建立控制面板。 本節內容僅適用於一般使用者和管理員。

使用者可基於下列幾個原因決定建立控制面板：

* 您可以從頭開始建立新控制面板，以便進行即時分析，而無需重複使用或共用控制面板。
* 您可以建立新控制面板，以執行您自己的個人分析，讓您儲存並重複使用，但不要共用。
* 您可以建立、儲存和共用新控制面板，供您和其他要存取的控制面板使用者人口使用。 無論如何，每個案例都會從相同的點開始：空白控制面板畫布。

>[!NOTE]
>
>開始建置控制面板之前，最好將「查詢至」百分比降至10%或25%之類的低值。 這樣就能比執行完整查詢更快從Data Workbench提取資料範例。 由於這些取樣結果的傳回速度快得多，因此在構建控制面板和分析時，可提供理想的回應能力。 準備好執行查詢以完成後，您可以將查詢完成參數更新為100%。 有關調整查詢完成的資訊，請參閱 [查詢對參數](../../../home/c-adobe-data-workbench-dashboard/c-dashboards/c-query-to-parameter.md#concept-33db106e28bc4108bca9e8d0a440d323).

若要建立新控制面板，請選取 **[!UICONTROL New]** 下。

![](assets/new_dashboard.png)

畫面會顯示空白的控制面板畫布，您可依據您的分析需求新增及設定視覺效果。 當您工作時，在您儲存之前，伺服器上不會有任何更新。

接下來，決定您要顯示哪種資料，以及要如何顯示。 通常從表格視覺化開始即可檢視原始資料，然後再建立其他圖表以符合需求。 如需新增和設定視覺效果的詳細資訊，請參閱 [建立視覺效果](../../../home/c-adobe-data-workbench-dashboard/c-visualizations/t-creating-visualizations.md#task-c6f1d20fa2484aeeb9a8487625054ecf). 新增並設定視覺效果以建置控制面板後，您最後會看到下列內容：

![](assets/after_configure.png)

從此，您只需執行分析並放棄控制面板，或者選擇將控制面板保存到伺服器以重複使用和/或共用。 如需如何與控制面板互動以執行分析的資訊，請參閱區段 [在控制面板中進行選取](../../../home/c-adobe-data-workbench-dashboard/c-making-selections-within-the-dashboard/c-making-selections-within-the-dashboard.md#concept-0989862de0044cc4bbfd7f4441275fc4).
