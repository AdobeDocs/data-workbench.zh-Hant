---
description: 「平面化」轉換會擷取字串向量，並將每個值對應至其專屬欄位。
title: Flatten
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Flatten{#flatten}

「平面化」轉換會擷取字串向量，並將每個值對應至其專屬欄位。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設 | 如果條件符合且輸入值不適用於記錄項目，則使用的預設值。 |  |
| 輸入 | 要映射到輸出欄位名稱的字串值向量。 |  |
| 輸出 | 一組輸出欄位名稱。 |  |

[!DNL Flatten]的注意事項

* 如果輸入向量包含的值比定義的輸出欄位多，則只會捨棄額外的輸入值。
* 如果輸入向量包含的值比定義的輸出欄位少，則額外的輸出欄位會指定預設值（如果已定義）或空字串（如果未定義預設值）。

在此，[!DNL Flatten]轉換用來取用產品的向量(x-products)，並將其分隔為四個欄位(x-product1, ..., x-product4)。

![](assets/cfg_TransformationType_Flatten.png)

如果輸入值包含字串B57481、C46355和Z97123，則輸出欄位將具有如下所示的值：

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 =空（輸入數多於輸出數，且未指定預設值）。
