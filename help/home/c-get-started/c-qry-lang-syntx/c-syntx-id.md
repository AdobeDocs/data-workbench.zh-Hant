---
description: 量度、維度和篩選器運算式可使用識別碼來參照命名的量度、維度和篩選器。
title: 識別碼的語法
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# 識別碼的語法{#syntax-for-identifiers}

{{eol}}

量度、維度和篩選器運算式可使用識別碼來參照命名的量度、維度和篩選器。

這些識別碼區分大小寫，且必須如實輸入。

有效識別碼可包含下列一或多個項目：

* 底線(_)。 識別碼中的底線代表量度、維度或篩選器名稱中的空格。 例如，「工作階段反向連結」維度可稱為 [!DNL Session_Referrer] 在運算式中。
* 百分比符號(%)
* 大寫字母(A-Z)
* 小寫字母(a-z)
* 美元符號($)
* 數字(0-9)，但作為標識符中的第一個字元除外。
* 非ASCII字元

所有其他字元在識別碼中均屬非法。

在運算式外使用量度、維度和篩選器時，這些相同的規則會套用至名稱，但名稱可包含空格，但不能包含底線。 例如，您可以在 [!DNL Transformation.cfg] 檔案做為工作階段反向連結，但不能 [!DNL Session_Referrer].
