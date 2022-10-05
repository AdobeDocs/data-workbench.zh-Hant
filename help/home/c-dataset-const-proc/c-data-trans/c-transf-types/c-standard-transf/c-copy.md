---
description: 複製轉換只會將輸入欄位中的值複製到指定的輸出欄位。 如果輸入欄位可以是字串的向量，則輸出欄位必須以「x — 」開頭。
title: 複製
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
exl-id: 04e97006-1e8e-4123-bbbc-b90a5231170f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 6%

---

# 複製{#copy}

{{eol}}

複製轉換只會將輸入欄位中的值複製到指定的輸出欄位。 如果輸入欄位可以是字串的向量，則輸出欄位必須以「x — 」開頭。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 若條件測試為true，且指定記錄項目中沒有輸入值可用，則使用。 |  |
| 輸入 | 要複製的欄位名稱。 |  |
| 輸出 | 輸出欄位的名稱。 |  |

在此範例中，使用從網站流量收集的資料欄位，每次cs-uri-stem符合時，輸出欄位x-purchase-success的文字值會指定為&quot;1&quot; [!DNL /checkout/confirmed.php]. 若 [!DNL Condition] 不滿意(即cs-uri-stem不匹配 [!DNL /checkout/confirmed.php]),x-purchase-success不會變更。

![](assets/cfg_TransformationType_Copy.png)
