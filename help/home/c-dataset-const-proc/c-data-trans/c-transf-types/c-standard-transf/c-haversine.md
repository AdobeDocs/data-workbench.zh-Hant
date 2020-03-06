---
description: 在數學上，哈弗森公式是一個方程，它給出了從其縱向和緯度上確定的球體上兩點之間的圓距離。
solution: Analytics
title: 哈韋辛
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 哈韋辛{#haversine}

在數學上，哈弗森公式是一個方程，它給出了從其縱向和緯度上確定的球體上兩點之間的圓距離。

和公式一樣，變 [!DNL Haversine] 換需要兩組和設定 [!DNL Latitude] ，用這四 [!DNL Longitude] 組輸入來計算兩個位置之間地球的真實距離。

通過將「In Krims」（公里）標誌從false更改為true，可將此距離表示為英里或公里。

![](assets/cfg_TransformationType_Haversine.png)

| 參數 | 說明 | 預設值 |
|---|---|---|
| 名稱 | 轉換的描述性名稱。 您可以在此輸入任何名稱。 |  |
| 意見 | 選填。關於轉變的附註。 |  |
| 條件 | 應用此轉換的條件。 |  |
| Latitude 1欄位 | 點1的緯度。 |  |
| Latitude 2現場 | 點2的緯度。 |  |
| 經度1欄位 | 點1的經度。 |  |
| 經度2欄位 | 點2的經度。 |  |
| 輸出 | 計算後，該字 [!DNL Output] 段包含指定為「尺寸」(Dimension)中元素的點之間的距離。 |  |

例如，如果您將其商店的經緯度編碼為Lat1、Lon1，並使用IP查閱lat和long給其客戶，則可確定大部分客戶購買或來自的商店的距離。

>[!NOTE]
>
>如果您想要識別其他位置的距離，則每個個別位置必須有其專屬的lat和lon欄位集。

