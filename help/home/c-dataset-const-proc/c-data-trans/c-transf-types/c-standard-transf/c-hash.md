---
description: 「雜湊」轉換會從輸入值建立幾乎唯一的字串，代表64位元數字。
title: Hash
uuid: 13bc14e6-75e2-4711-8f98-50fd18802be5
exl-id: 6912a1d2-9ae8-42ba-94bd-a7a28cbdfae6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 4%

---

# Hash{#hash}

「雜湊」轉換會從輸入值建立幾乎唯一的字串，代表64位元數字。

此轉換在給定相同的輸入時提供相同的散列值。

>[!NOTE]
>
>產生的值幾乎是唯一的，因為轉換使用64位元數字作為可能的雜湊值空間。 對於[!DNL hash]轉換的100萬個唯一輸入，有1/38,000,000的機會獲得重複的雜湊值。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設 | 如果輸入值不可用，則使用的預設值。 |  |
| 輸入 | 用於建立散列值的一組輸入。 |  |
| 輸出 | 輸出的欄位名稱。 |  |

在此範例中，c-ip和cs(user-agent)欄位的值可用來建立追蹤ID，並儲存在x-trackingid欄位中。

![](assets/cfg_TransformationType_Hash.png)

>[!NOTE]
>
>此範例不代表建立唯一追蹤ID的理想解決方案。 但是，在使用歸檔日誌資訊的情況下，它可能是最佳的方法。
