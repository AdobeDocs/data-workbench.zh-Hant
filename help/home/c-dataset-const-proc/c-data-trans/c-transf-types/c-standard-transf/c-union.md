---
description: Union轉換採用一組輸入，並建立字串向量作為輸出。
title: Union
uuid: 2f8bd332-727e-4a4e-a3e7-a52ea2b0a33a
exl-id: 841b5133-d587-409c-b39e-47169beb2ddf
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 3%

---

# Union{#union}

Union轉換採用一組輸入，並建立字串向量作為輸出。

如果其中一個輸入本身是向量，則輸入向量中的每個元素與輸出向量中的一個元素相關聯（即，變換不建立向量的向量）。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設 | 如果條件符合且輸入值不可用，則使用的預設值。 |  |
| 輸入 | 一個或多個輸入值。 |  |
| 輸出 | 輸出欄位的名稱。 |  |

此範例使用網站流量的資料欄位來建立與網站訪客相關的郵遞區號清單（即，在每個記錄項目內）。 這些資料提供了兩種可能的資訊來源：一個位於cs-uri-query，另一個位於Cookie的[!DNL zipcode]欄位。 如果這兩個欄位中都未包含郵遞區號，則會使用預設值00000。

![](assets/cfg_TransformationType_Union.png)

雖然這兩個值都可以在單個日誌條目中使用，但可以根據轉換的輸出選擇建立維時要使用的值。 在典型的使用案例中，您會建立一個簡單維度，其中會使用第一個或最後一個所遇到的值。 有關建立簡單維的資訊，請參閱[擴展Dimension](../../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。
