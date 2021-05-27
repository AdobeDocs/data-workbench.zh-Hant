---
description: ChangeCase轉換將更改Action參數所指定的Input參數中字串的大小寫。
title: ChangeCase
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
exl-id: 2002fe22-d31c-4286-9f73-59ef205f1384
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 8%

---

# ChangeCase{#changecase}

ChangeCase轉換將更改Action參數所指定的Input參數中字串的大小寫。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 動作 | 上或下。 指定大小寫要變更為上或下。 | lower |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 輸入 | 要作為輸入的日誌條目中的欄位名稱。 |  |
| 輸出 | 輸出欄位的名稱。 |  |

在此範例中，使用從網站流量收集的資料欄位，s-dns欄位內的字串大小寫會變更為小寫，而新值會在新欄位x-lowercase-dns中輸出。

![](assets/cfg_TransformationType_ChangeCase.png)
