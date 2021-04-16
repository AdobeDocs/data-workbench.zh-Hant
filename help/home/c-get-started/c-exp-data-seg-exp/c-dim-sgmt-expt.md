---
description: 要導出的任何資料都必須定義為配置檔案中的維。
title: 建立維度以便與區段匯出功能搭配使用
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# 建立維度以便與區段匯出功能搭配使用{#create-dimensions-for-use-with-segment-export}

要導出的任何資料都必須定義為配置檔案中的維。

如果該維在配置檔案中尚未存在，則必須建立它。 您可以使用下列任何方法來建立維度：

* 將維添加到[!DNL Transformation.cfg]檔案。 請參閱&#x200B;*資料集設定指南*。

* 建立新的[!DNL .dim]檔案。 請參閱[建立和編輯派生Dimension](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)。

* 在視覺化（例如流程圖或區段）中選取範圍，並將選取範圍儲存為維度。 請參閱[保存流程映射中的Dimension](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051)和[建立段Dimension](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)。

匯出資料欄位(例如追蹤ID或電子郵件地址（可包含許多元素）)需要您建立非正規維度，以儲存資料的原始字串。

如需非正規維度的詳細資訊，請參閱&#x200B;*資料集設定指南*。
