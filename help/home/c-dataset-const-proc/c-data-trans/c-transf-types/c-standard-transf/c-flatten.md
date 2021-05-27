---
description: 平面化轉換會取用字串向量，並將每個值對應至其自己的欄位。
title: Flatten
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Flatten{#flatten}

平面化轉換會取用字串向量，並將每個值對應至其自己的欄位。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 在符合條件且輸入值無法用於記錄項目時使用的預設值。 |  |
| 輸入 | 要映射到輸出欄位名稱的字串值的向量。 |  |
| 輸出 | 一組輸出欄位名稱。 |  |

[!DNL Flatten]的考量事項

* 如果輸入向量包含的值多於定義的輸出欄位，則只會捨棄額外的輸入值。
* 如果輸入向量包含的值少於定義的輸出欄位，則額外的輸出欄位將指定預設值（如果已定義），如果未定義預設值，則為空字串。

在此，[!DNL Flatten]轉換用於取用產品向量(x-products)，並將它們分隔為四個欄位(x-product1, ..., x-product4)。

![](assets/cfg_TransformationType_Flatten.png)

如果輸入值包含字串B57481、C46355和Z97123，則輸出欄位會有以下所示的值：

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 =空（輸入數多於輸出數，且未指定預設值）。
