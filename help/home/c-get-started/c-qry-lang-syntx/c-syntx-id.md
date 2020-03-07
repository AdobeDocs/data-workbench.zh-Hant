---
description: 量度、維度和篩選運算式可使用識別碼來參照命名量度、維度和篩選。
solution: Analytics
title: 識別碼的語法
topic: Data workbench
uuid: 9cfa188a-05ca-4163-a268-e33fce9a1929
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 識別碼的語法{#syntax-for-identifiers}

量度、維度和篩選運算式可使用識別碼來參照命名量度、維度和篩選。

這些識別碼區分大小寫，且必須依其定義正確輸入。

有效的識別碼可以包含下列一或多個：

* 下划線(_)。 識別碼中的底線代表量度、維度或篩選器名稱中的空格。 例如，「作業反向連結」維度在運算式中 [!DNL Session_Referrer] 會稱為。
* 百分比符號(%)
* 大寫字母(A-Z)
* 小寫字母(a-z)
* 美元符號($)
* 數字(0-9)，但作為標識符中的第一個字元除外。
* 非ASCII字元

所有其他字元在識別碼中都是非法的。

當量度、維度和篩選器在運算式外部使用時，這些相同規則會套用至其名稱，但名稱可包含空格，而非底線。 例如，您可以將檔案中的「工作階段反向連結」維度定 [!DNL Transformation.cfg] 義為「工作階段反向連結」，但不能 [!DNL Session_Referrer]。
