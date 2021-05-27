---
description: PullNameValues轉換是一種特殊操作，它採用cs-uri-query欄位中的值，並將每個名稱 — 值對分隔成單獨的字串。
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

PullNameValues轉換是一種特殊操作，它採用cs-uri-query欄位中的值，並將每個名稱 — 值對分隔成單獨的字串。

名稱值對字串的整個集合在指定的輸出欄位中輸出為字串的向量。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 在符合條件且指定記錄項目中無法使用輸入值時要使用的預設值。 |  |
| 輸出 | 輸出字串的名稱。 |  |

此範例中使用[!DNL PullNameValues]轉換來擷取訪客對搜尋表單的使用：已選取哪些按鈕、在表單中輸入了哪些值等。 此範例使用[!DNL String Match]條件（請參閱[條件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)），將此轉換的使用隔離至僅頁面[!DNL /search.php]。 名稱值配對的向量會輸出至欄位x-search-namevalues。

![](assets/cfg_TransformationType_PullNameValues.png)

使用如上定義的轉換，如果cs-uri-stem欄位符合頁面[!DNL /search.php]和cs-uri-query包含下列內容：

* Searchfor=Bob&amp;State=Virginia&amp;isMale=true

然後x-search-namevalues會包含包含下列三個字串的向量：

* Searchfor=Bob
* 州=維吉尼亞
* isMale=true
