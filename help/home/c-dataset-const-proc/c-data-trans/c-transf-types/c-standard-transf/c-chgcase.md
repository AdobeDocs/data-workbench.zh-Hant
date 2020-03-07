---
description: ChangeCase轉換將更改Input參數中由Action參數指定的字串的大小寫。
solution: Analytics
title: ChangeCase
topic: Data workbench
uuid: 676e79e6-324e-43d1-8982-b44596d0eeac
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ChangeCase{#changecase}

ChangeCase轉換將更改Input參數中由Action參數指定的字串的大小寫。

| 參數 | 說明 | 預設值 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 動作 | 上下。 指定大小寫是更改為上方還是下方。 | lower |
| 意見 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 輸入 | 要用作輸入的日誌條目中的欄位的名稱。 |  |
| 輸出 | 輸出欄位的名稱。 |  |

在此範例中，使用從網站流量收集到的資料欄位，s-dns欄位中的字串大小寫會變更為小寫，新值會輸出到新欄位x-lowercase-dns。

![](assets/cfg_TransformationType_ChangeCase.png)

