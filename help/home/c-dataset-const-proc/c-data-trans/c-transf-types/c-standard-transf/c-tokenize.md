---
description: Tokenize變換迭代地對輸入字串應用規則表達式。
title: Tokenize
uuid: f8430e6c-ec14-4ba6-aeae-92c9f2520a63
exl-id: c1f39b5b-4717-44f6-99c7-4e6a215f3542
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 4%

---

# Tokenize{#tokenize}

{{eol}}

Tokenize變換迭代地對輸入字串應用規則表達式。

不過，與 [!DNL RETransform], [!DNL Tokenize] 不必符合整個字串：用於 [!DNL Tokenize] 轉換可以匹配輸入的子集。 找到相符項目後， [!DNL Tokenize] 再次套用規則運算式，從上次相符項目結尾後的字元開始。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 區分大小寫 | True或False。 指定匹配是否區分大小寫。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 在符合條件且輸入值不可用或規則運算式不符合輸入值時，要使用的預設值。 |  |
| 運算式 | 用於比對的規則運算式。 |  |
| 輸出 | 輸出字串的名稱。 您可以為指定的輸入字串提供多個輸出。 輸出數必須與規則運算式中擷取子模式的數量相對應。 |  |

在下列範例中， [!DNL Tokenize] 轉換使用規則運算式來擷取查詢字串的名稱（在cs-uri-query中），並將擷取的子模式（查詢名稱）輸出為x-pull-query-name。

![](assets/cfg_TransformationType_Tokenize.png)

若為查詢字串&quot;a=b&amp;c=d&quot;，輸出會是包含&quot;a&quot;和&quot;c&quot;的向量。

如需規則運算式的相關資訊，請參閱 [規則運算式](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).
