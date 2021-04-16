---
description: 「取消轉義URI」轉換會取消轉義已逸出的字串中的任何字元。
title: UnescapeURI
uuid: 25e87cc7-812d-4d77-be94-16093e8955fe
exl-id: abf20906-5052-4bbe-9ffb-522b850669a6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 6%

---

# UnescapeURI{#unescapeuri}

「取消轉義URI」轉換會取消轉義已逸出的字串中的任何字元。

>[!NOTE]
>
>逸出字元會取代URI字串中不安全的字元。 它們由三位元組成，由百分比符號和兩個十六進位數字（例如%20）組成。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設 | 如果條件符合且輸入值不可用，則使用的預設值。 |  |
| 輸入 | 要取消逸出的URI字串。 |  |
| 輸出 | 要儲存未逸出字串的欄位的名稱。 |  |

以下轉換會取消轉義HTTP標題欄位中的docname值，並將輸出儲存在欄位x-docname-unescape中：

![](assets/cfg_TransformationType_UnescapeURI.png)

如果docname值

* [!DNL mysite.net/lending%20and%20leasing%20forms/document%20library/credit%20application.doc]

x-docname-unescape的值將是

* [!DNL mysite.net/lending and leasing forms/document library/credit application.doc]
