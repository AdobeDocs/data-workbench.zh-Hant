---
description: 關於協力廠商標籤和使用P3P防止Cookie封鎖的概念資訊。
title: 第三方頁面標記的 P3P 考量事項
uuid: b88d0d22-0ff8-4b63-9be9-7acc12061146
exl-id: 8eb521b6-802c-4d9f-a6b4-b1c4f694b8b8
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# 第三方頁面標記的 P3P 考量事項{#p-p-considerations-for-third-party-page-tagging}

關於協力廠商標籤和使用P3P防止Cookie封鎖的概念資訊。

## 了解第三方頁面標籤 {#section-8dc5b6b99e454ef7a7cf578ebbf9efca}

在大部分實作中，Adobe永久性Cookie會視為第一方Cookie。 第一方Cookie定義為與主機網域相關聯的Cookie。

假設有使用者造訪https://www.example.com/ 。 假設已安裝Sensor且可在托管網域的Web伺服器上運作，則會設定Adobe永續性Cookie，並將其視為第一方Cookie。 但是，您可能希望使用內嵌物件來收集來自第三方網站的測量資料，這些物件會從執行[!DNL Sensor]的伺服器（而非托管頁面或廣告程式的第三方伺服器）要求並載入。 例如， https://www.example2.com/會提供網頁，其中包含https://www.example.com/所提供的內嵌物件要求。 https://www.example.com/的內嵌物件要求會導致Cookie設定；不過，在此情境下，網頁瀏覽器或使用者代理會將cookie檢視為協力廠商cookie。

在Microsoft的IE6等較新的網頁瀏覽器中，隱私權功能會根據Web伺服器HTTP回應標題中傳送的精簡版原則來篩選Cookie。 在大部分使用者永不變更的預設IE6設定中，當第三方Cookie不存在或精簡政策不理想時，就會封鎖這些Cookie。 遇到Cookie封鎖問題的大部分網站，其網站上都有第三方Cookie，且HTTP回應標題中未傳送適當的壓縮原則。 此外，當網站由其他網站組態時，也會發生一些Cookie封鎖問題。 例如，屬於線上購物入口的線上商店可能顯示在入口提供的框架中。 從瀏覽器的角度來看，當入口網站設定框架時，商店內容可能會看起來是第三方內容。 不過，如果訪客未經入口網站直接前往線上商店，內容將是第一方內容。 因此，線上商店發現，只有當訪客透過入口進入時，其Cookie才會遭到封鎖。

基於Web的郵件系統造成類似的問題。 如果網站訪客將網頁電子郵件傳送給使用網頁型郵件系統的朋友，則電子郵件訊息會以第三方內容的形式顯示給朋友的瀏覽器，因為該內容是由電子郵件系統所構架。 如果有任何Cookie與以電子郵件傳送的頁面相關聯，則IE6會將它們視為第三方Cookie。

## 使用P3P防止Cookie封鎖 {#section-96831cad887649f295aec6931750e41a}

P3P為網站提供標準方式，以電腦可讀的XML格式將其隱私權政策編碼。 啟用P3P的網頁瀏覽器和其他P3P使用者代理會自動擷取P3P隱私權原則、加以剖析，並與使用者的隱私權偏好設定進行比較。

若要防止IE6封鎖您網站上的Cookie，您必須確保：

1. 所有在協力廠商內容中設定的Cookie，都有與其相關聯的P3P壓縮原則。
1. 使用自訂HTTP回應標頭來傳送適當的壓縮原則。
1. IE6認為這些緊湊政策令人滿意。
1. 如果第三方Cookie是由其他公司設定，您可能需要要求他們啟用P3P並設定P3P緊密政策。 任何設定P3P壓縮策略的主機也必須具有相應的完整P3P策略。 使用者可以變更其IE6設定，以便在其他條件下也封鎖Cookie;不過，對第三方cookie放置滿意的緊密政策，可防止大部分的IE6cookie封鎖。

以下是此類P3P標題的範例：

```
P3P: policyref=” https://www.myserver.com/w3c/p3p.xml”, CP=”NOI DSP COR PSA PSD OUR IND COM NAV”
```

在此示例中，檔案[!DNL p3p.xml]用於引用駐留在Web伺服器上的關聯[!DNL policy.xml]檔案，該檔案表示您的網站收集的資訊種類、您的組織遵守的爭議解決方法、收集的資料的使用方式、擁有資料的人員以及與Internet隱私相關的其他標準資訊。 &quot;CP&quot;後面的三個字元代碼是模擬[!DNL policy.xml]檔案中所述內容的精簡策略代碼。

所有精簡的策略和策略XML檔案都應針對部署的組織進行定制，並準確指定其有關網站資料收集的內部隱私策略。 您可以線上找到許多P3P原則編輯器，以及與在網站中實施適當隱私權原則相關的更深入資訊。

有關Internet Explorer 6如何處理P3P標題的詳細資訊，請訪問：

[https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp](https://msdn.microsoft.com/library/default.asp?url=/library/en-us/dnpriv/html/ie6privacyfeature.asp)
