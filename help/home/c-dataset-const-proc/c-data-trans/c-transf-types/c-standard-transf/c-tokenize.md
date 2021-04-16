---
description: Tokenize變換反覆地對輸入字串應用規則運算式。
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 5%

---

# Tokenize{#tokenize}

Tokenize變換反覆地對輸入字串應用規則運算式。

但是，與[!DNL RETransform]不同，[!DNL Tokenize]不必符合整個字串：用於[!DNL Tokenize]轉換的規則運算式可以匹配輸入的子集。 找到匹配後，[!DNL Tokenize]將再次應用規則運算式，從上次匹配結束後的字元開始。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 區分大小寫 | True 或 False. 指定匹配是否區分大小寫。 |  |
| 註解 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設 | 如果條件符合且輸入值不可用或規則運算式不符合輸入值，則使用的預設值。 |  |
| 運算式 | 用於匹配的規則運算式。 |  |
| 輸出 | 輸出字串的名稱。 您可針對指定的輸入字串提供多個輸出。 輸出數必須與規則運算式中擷取子模式的數目相對應。 |  |

在以下範例中，[!DNL Tokenize]轉換使用規則運算式來擷取查詢字串的名稱（在cs-uri-query中），並將擷取的子模式（查詢名稱）輸出為x-pull-query-name。

![](assets/cfg_TransformationType_Tokenize.png)

對於查詢字串&quot;a=b&amp;c=d&quot;，輸出會是包含&quot;a&quot;和&quot;c&quot;的向量。

有關規則運算式的資訊，請參見[規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c)。
