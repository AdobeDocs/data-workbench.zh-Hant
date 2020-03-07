---
description: 「複製」(Copy)轉換只會將輸入欄位中的值複製到給定的輸出欄位。 如果輸入欄位可以是字串的向量，輸出欄位必須以"x-"開頭。
solution: Analytics
title: 複製
topic: Data workbench
uuid: 073f53bf-befb-4fba-a8f8-260ffcdd007c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 複製{#copy}

「複製」(Copy)轉換只會將輸入欄位中的值複製到給定的輸出欄位。 如果輸入欄位可以是字串的向量，輸出欄位必須以&quot;x-&quot;開頭。

| 參數 | 說明 | 預設值 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 意見 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設值 | 如果條件測試為true且輸入值在給定日誌條目中不可用，則使用。 |  |
| 輸入 | 要從中複製的欄位的名稱。 |  |
| 輸出 | 輸出欄位的名稱。 |  |

在此範例中，使用從網站流量收集到的資料欄位，每次cs-uri-stem符合時，輸出欄位x-purchase-success的常值為&quot;1&quot; [!DNL /checkout/confirmed.php]。 如果 [!DNL Condition] 不符合(即cs-uri-stem不符合 [!DNL /checkout/confirmed.php]),x-purchase-success不會變更。

![](assets/cfg_TransformationType_Copy.png)

