---
description: ReplaceURI轉換將內部URI維中的值更改為新值。
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

ReplaceURI轉換將內部URI維中的值更改為新值。

如果指定[!DNL URI Prefix]，則產生的值只是與提供的輸入值串連的URI前置詞。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 在符合條件且輸入值不可用時使用的預設值。 |  |
| 輸入 | 要替換URI的值。 |  |
| URI前置詞 | 要在[!DNL Input]欄位中的值前面加上的值（字串）。 |  |

>[!NOTE]
>
>在應用[!DNL ReplaceURI]轉換之前，應從cs-uri-stem或cs-uri的副本建立父級為[!DNL Page View]的新簡單維。 如需相關協助，請聯絡Adobe。

此範例示範當&#x200B;*pageid*&#x200B;指出已檢視網站首頁時，使用[!DNL ReplaceURI]將&quot;page=*pageid*&quot;查詢字串取代為&quot; [!DNL homepage.html]&quot;。 最終結果是URI的更易用視圖。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

針對顯示的轉換，頁面

* [!DNL www.examplesite.com/info.html?page=1550]

會變更為

* [!DNL www.examplesite.com/homepage.html]
