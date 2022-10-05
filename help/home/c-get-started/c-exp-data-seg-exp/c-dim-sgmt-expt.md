---
description: 您要匯出的任何資料都必須在設定檔中定義為維度。
title: 建立維度以便與區段匯出功能搭配使用
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# 建立維度以便與區段匯出功能搭配使用{#create-dimensions-for-use-with-segment-export}

{{eol}}

您要匯出的任何資料都必須在設定檔中定義為維度。

如果設定檔中尚未存在維度，您必須建立它。 您可以使用下列任何方法來建立維度：

* 新增維度至 [!DNL Transformation.cfg] 檔案。 請參閱 *資料集組態指南*.

* 建立新 [!DNL .dim] 檔案。 請參閱 [建立和編輯衍生Dimension](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* 在視覺效果（例如程式圖或區段）中進行選取，並將選取項目儲存為維度。 請參閱 [從流程圖中保存Dimension](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) 和 [建立區段Dimension](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

匯出資料欄位(例如「追蹤ID」或「電子郵件地址」（可以有許多元素）時，需要您建立非正規維度，以儲存原始資料字串。

如需非正規維度的詳細資訊，請參閱 *資料集組態指南*.
