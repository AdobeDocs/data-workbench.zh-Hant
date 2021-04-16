---
description: 量度、維度和篩選運算式可使用識別碼來參照命名量度、維度和篩選。
title: 識別碼的語法
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
exl-id: 79bc5585-7b21-4a9d-b044-28ff4bc5a885
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 3%

---

# 識別碼的語法{#syntax-for-identifiers}

量度、維度和篩選運算式可使用識別碼來參照命名量度、維度和篩選。

這些識別碼區分大小寫，且必須依其定義正確輸入。

有效的識別碼可以包含下列一或多個：

* 下划線(_)。 識別碼中的底線代表量度、維度或篩選器名稱中的空格。 例如，運算式中的「工作階段反向連結」維度會稱為[!DNL Session_Referrer]。
* 百分比符號(%)
* 大寫字母(A-Z)
* 小寫字母(a-z)
* 美元符號($)
* 數字(0-9)，但作為標識符中的第一個字元除外。
* 非ASCII字元

所有其他字元在識別碼中都是非法的。

當量度、維度和篩選器在運算式外部使用時，這些相同規則會套用至其名稱，但名稱可包含空格，而非底線。 例如，您可將[!DNL Transformation.cfg]檔案中的「工作階段反向連結」維度定義為「工作階段反向連結」，但不能定義為[!DNL Session_Referrer]。
