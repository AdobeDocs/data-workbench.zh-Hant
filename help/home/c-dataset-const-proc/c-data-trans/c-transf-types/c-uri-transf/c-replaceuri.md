---
description: ReplaceURI轉換會將內部URI維中的值更改為新值。
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

ReplaceURI轉換會將內部URI維中的值更改為新值。

如果指定[!DNL URI Prefix]，則產生的值只是與提供的輸入值串連的URI首碼。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設 | 如果條件符合且輸入值不可用，則使用的預設值。 |  |
| 輸入 | 替換URI的值。 |  |
| URI前置詞 | 值（字串）會附加在[!DNL Input]欄位中的值之前。 |  |

>[!NOTE]
>
>在套用[!DNL ReplaceURI]轉換之前，您應從cs-uri-stem或cs-uri的復本建立父項為[!DNL Page View]的新簡單維度。 如需協助，請聯絡Adobe。

此範例示範當&#x200B;*pageid*&#x200B;指出已檢視網站首頁時，使用[!DNL ReplaceURI]將&quot;page=*pageid*&quot;查詢字串取代為&quot;[!DNL homepage.html]&quot;。 最終結果是URI的更易用視圖。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

對於顯示的轉換，頁面

* [!DNL www.examplesite.com/info.html?page=1550]

會變更為

* [!DNL www.examplesite.com/homepage.html]
