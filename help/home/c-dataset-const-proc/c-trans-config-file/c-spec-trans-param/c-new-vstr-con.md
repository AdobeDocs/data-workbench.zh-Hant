---
description: 「新訪客條件」是「條件操作」，用於判斷要將哪些訪客納入資料集。
title: 新訪客條件
uuid: e9733109-5bf3-47ce-974c-d68264291f19
exl-id: a0520edd-bde3-4f55-858c-8974d4224435
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 3%

---

# 新訪客條件{#new-visitor-condition}

「新訪客條件」是「條件操作」，用於判斷要將哪些訪客納入資料集。

[!DNL New Visitor Condition]會定義資料集中要使用的訪客的第一個記錄項目（依時間排序），而無論該訪客是否符合此條件，該訪客的所有後續記錄項目都會納入資料集中。 因為[!DNL New Visitor Condition]要求資料依訪客和時間排序，因此只有在資料集建構的轉換階段才會套用。

此範例中顯示的[!DNL New Visitor Condition]會為回應電子郵件促銷活動的訪客建立僅包含這些記錄項目的資料集。 這是使用[!DNL NotEmptyCondition]測試（請參閱[非空白](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-op-con.md#section-1decb9d887894073a1b6b3d985729ac8)）和[!DNL x-campaign-email]欄位作為規則運算式的輸入來完成的。 識別符合條件的新訪客後，即會擷取這些訪客的所有記錄項目。

![](assets/cfg_Transformation_NewVisitorCondition.png)
