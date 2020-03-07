---
description: ReplaceURI轉換會將內部URI維中的值更改為新值。
solution: Analytics
title: ReplaceURI
topic: Data workbench
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# ReplaceURI{#replaceuri}

ReplaceURI轉換會將內部URI維中的值更改為新值。

如果 [!DNL URI Prefix] 指定，則結果值只是與提供的輸入值串連的URI前置詞。

| 參數 | 說明 | 預設值 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 意見 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| 預設值 | 如果條件符合且輸入值不可用，則使用的預設值。 |  |
| 輸入 | 替換URI的值。 |  |
| URI前置詞 | 要附加在欄位中之值的值（字串） [!DNL Input] 。 |  |

>[!NOTE]
>
>在套用 [!DNL ReplaceURI] 轉換之前，您應先從cs-uri-stem或cs-uri復 [!DNL Page View]本建立父項為的新簡單維度。 如需相關協助，請聯絡Adobe。

此範例示範當 [!DNL ReplaceURI] pageid指出已檢視網站首頁時，使用&quot;*&quot;來取代&quot;page=* pageid [!DNL homepage.html]** &quot;查詢字串。 最終結果是URI的更易用視圖。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

對於顯示的轉換，頁面

* [!DNL www.examplesite.com/info.html?page=1550]

會變更為

* [!DNL www.examplesite.com/homepage.html]

