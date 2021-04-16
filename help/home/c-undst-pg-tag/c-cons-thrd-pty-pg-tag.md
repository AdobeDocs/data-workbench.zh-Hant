---
description: 有關使用P3P進行第三方標籤及防止Cookie封鎖的概念性資訊。
title: 第三方頁面標記的 P3P 考量事項
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# 第三方頁面標記的 P3P 考量事項{#p-p-considerations-for-third-party-page-tagging}

有關使用P3P進行第三方標籤及防止Cookie封鎖的概念性資訊。

## 瞭解第三方頁面標籤{#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

在大部分實作中，Adobe永久性Cookie會視為第一方Cookie。 第一方Cookie定義為與主機網域關聯的Cookie。

假設有使用者造訪http://www.example.com/。 假設感測器已安裝並可在托管網域的Web伺服器上運作，則會設定Adobe永久性Cookie，並視為第一方Cookie。 不過，您可能想要透過使用內嵌物件從第三方網站收集測量資料，這些物件會從執行[!DNL Sensor]的伺服器要求並載入，而非從代管頁面或廣告程式的第三方伺服器。 例如，http://www.example2.com/會提供網頁，其中內嵌的物件要求會從http://www.example.com/取得。 http://www.example.com/對內嵌物件的要求會導致Cookie設定；不過，在此情境中，網頁瀏覽器或使用者代理會將Cookie檢視為第三方Cookie。

在較新的Web瀏覽器（例如Microsoft的IE6）中，隱私權功能會根據Cookies從Web伺服器傳送的HTTP回應標題中所傳送的精簡原則來篩選Cookie。 在大部分使用者不會變更的預設IE6設定中，當第三方Cookie不存在或無法令人滿意的精簡版政策時，就會封鎖它們。 大多數遇到Cookie封鎖問題的網站，其網站上都有第三方Cookie，而第三方Cookie沒有在HTTP回應標題中傳送適當的精簡版原則。 此外，當網站由其他網站組態時，會發生一些Cookie封鎖問題。 例如，屬於線上購物入口網站一部分的線上商店可能會出現在入口網站提供的框架中。 從瀏覽器的角度來看，當入口網站設定框架時，商店內容可能會看起來像是第三方內容。 不過，如果訪客直接進入線上商店而未透過入口網站，則內容將是第一方內容。 因此，線上商店只會在訪客透過入口網站進入時發現其Cookie遭到封鎖。

基於Web的郵件系統也會導致類似問題。 如果網站訪客將網頁電子郵件傳送給使用網路郵件系統的朋友，則電子郵件訊息會以第三方內容的形式顯示給朋友的瀏覽器，因為該電子郵件系統會以電子郵件系統為框架。 如果有任何與透過電子郵件傳送之頁面相關聯的Cookie,IE6會將其視為第三方Cookie。

## 使用P3P防止Cookie封鎖{#section-96831cad887649f295aec6931750e41a}

P3P為網站提供標準方式，以電腦可讀的XML格式來編碼其隱私權政策。 啟用P3P的網頁瀏覽器和其他P3P使用者代理會自動擷取P3P隱私權政策、加以剖析，並與使用者的隱私權偏好設定進行比較。

若要防止IE6封鎖您網站上的Cookie，您必須確保：

1. 在協力廠商內容中設定的所有Cookie都有與其關聯的P3P精簡版政策。
1. 使用自訂HTTP回應標題來傳送適當的精簡原則。
1. IE6認為這些契約政策令人滿意。
1. 如果協力廠商Cookie是由其他公司設定，您可能需要要求他們啟用P3P並設定P3P精簡版政策。 任何設定P3P精簡原則的主機也必須有對應的完整P3P原則。 使用者可以變更其IE6設定，以便在其他情況下也封鎖Cookie;但是，在協力廠商Cookie上放置令人滿意的精簡版原則可防止大部分的IE6 Cookie封鎖。

以下是此類P3P標題的範例：

```
P3P: policyref=” http://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

在此範例中，檔案[!DNL p3p.xml]用於參考位於網站伺服器上的相關[!DNL policy.xml]檔案，該檔案表示您的網站所收集的資訊類型、您組織所遵守的爭議解決方法、所收集資料的使用方式、資料的擁有者，以及其他與網際網路隱私權相關的標準資訊。 &quot;CP&quot;後面的三個字元代碼是模擬[!DNL policy.xml]檔案中所述內容的精簡策略代碼。

所有精簡的政策和原則XML檔案都應針對所部署的組織量身打造，以精確指定其網站資料收集的內部隱私權政策。 您可線上上找到許多P3P政策編輯器，以及在您的網站中實施適當隱私權政策的相關深入資訊。

如需Internet Explorer 6如何處理P3P標題的詳細資訊，請造訪：

[http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
