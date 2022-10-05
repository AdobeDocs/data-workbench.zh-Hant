---
description: ReplaceURI轉換將內部URI維中的值更改為新值。
title: ReplaceURI
uuid: f9fc6d51-6eb6-4ace-8c19-2c0200555363
exl-id: 03a6f306-5e2e-488c-8d79-a14938dcd635
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 5%

---

# ReplaceURI{#replaceuri}

{{eol}}

ReplaceURI轉換將內部URI維中的值更改為新值。

若 [!DNL URI Prefix] 指定後，產生的值只是與提供的輸入值串連的URI前置詞。

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 預設 | 在符合條件且輸入值不可用時使用的預設值。 |  |
| 輸入 | 要替換URI的值。 |  |
| URI前置詞 | 要加到 [!DNL Input] 欄位。 |  |

>[!NOTE]
>
>套用前 [!DNL ReplaceURI] 轉換時，應建立新的簡單維，其父維為 [!DNL Page View]來自cs-uri-stem或cs-uri的副本。 如需相關協助，請聯絡Adobe。

此範例示範如何使用 [!DNL ReplaceURI] 取代「page=」*pageid*&quot;查詢字串 [!DNL homepage.html]&quot;每當 *pageid* 表示已檢視網站的首頁。 最終結果是URI的更易用視圖。

![](assets/cfg_TransformationType_ReplaceURI.bmp)

針對顯示的轉換，頁面

* [!DNL www.examplesite.com/info.html?page=1550]

會變更為

* [!DNL www.examplesite.com/homepage.html]
