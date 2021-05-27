---
description: 在數學中，哈佛斯公式是一個方程，它給出從其經緯度確定的球體上兩點之間的圓距離。
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# 哈弗西內{#haversine}

在數學中，哈佛斯公式是一個方程，它給出從其經緯度確定的球體上兩點之間的圓距離。

與公式一樣，[!DNL Haversine]轉換需要兩組[!DNL Latitude]和[!DNL Longitude]設定，使用這四個輸入計算兩個位置之間地球的真實距離。

將「公里內」標幟從false變更為true，即可將此距離表示為英里或公里。

![](assets/cfg_TransformationType_Haversine.png)

| 參數 | 說明 | 預設 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 註解 | 選填。轉換的相關附註。 |  |
| 條件 | 套用此轉換的條件。 |  |
| 緯度1欄位 | 點1的緯度。 |  |
| Latitude 2欄位 | 點2的緯度。 |  |
| 經度1欄位 | 點1的經度。 |  |
| 經度2欄位 | 點2的經度。 |  |
| 輸出 | 計算後，[!DNL Output]欄位包含指定為Dimension中元素的點之間的距離。 |  |

例如，如果您在其商店的經緯度以Lat1、Lon1編碼，並對其客戶使用IP查閱lat和long，則可判斷與大多數客戶購買或來自的商店的距離。

>[!NOTE]
>
>如果您想要識別其他位置的距離，則每個個別位置都必須有其專屬的緯度欄位和長欄位集。
