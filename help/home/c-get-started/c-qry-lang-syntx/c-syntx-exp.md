---
description: 公式的語法規則。
solution: Analytics
title: 任何運算式的語法
topic: Data workbench
uuid: 663e3fd2-80e5-4805-8706-34a0e02ebd0f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 任何運算式的語法{#syntax-for-any-expression}

公式的語法規則。

* 在公式中時，關鍵字會區分大小寫，且必須依其顯示方式正確輸入。
* 在公式中，包含空格的量度、維度和篩選名稱必須在字詞之間使用底線。 例如︰[!DNL Page_Views]
* 對於運算式中的字串，您必須逸出某些單引號、雙引號和反斜線。 例如：

   * [!DNL “can’t”] 可接受且不需要逸出，但是不可 [!DNL ‘can’t’] 接受，必須逸出 [!DNL ‘can\’t’]。

   * [!DNL c:\windows] 必須逸出為 [!DNL c:\\windows]。

