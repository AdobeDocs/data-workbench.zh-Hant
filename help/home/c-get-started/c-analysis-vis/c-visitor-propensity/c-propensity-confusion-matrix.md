---
description: 已定義「傾向分數」的統計計算。
title: 計算傾向分數
uuid: 67270864-0468-4cc9-b48b-0e880f813555
exl-id: 679e1363-fd10-4a44-a85a-ef0daefaf303
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 1%

---

# 計算傾向分數{#calculating-propensity-scoring}

{{eol}}

已定義「傾向分數」的統計計算。

從概念上講，為每個訪客計算的分數是指定事件（由目標篩選器定義）可能發生的預估機率，因此分數值範圍從0到100%。 評分程式使用現有樣本作為訓練資料，以尋找事件概率與所選取的獨立關注變數之間的關係。

從數學上講，這些關係反映在與每個獨立變數相關聯的每個量化值中。 這些值稱為模型系數。 ScoreDim目前使用迭代重加權最小二乘(IRLS)算法來估計模型系數。 IRLS多次通過樣本，直到電流通道與前次通道之間系數的差值小於1.0e-6，此時稱為 **融合**. 但是，根據資料，IRLS可能無法達到收斂。

在這種情況下，模型訓練迭代將在

* 系數差變大，
* 已到達1,000次通行，或
* 數學錯誤會阻止繼續迭代。

如果IRLS不收斂，則將使用一種稱為隨機梯度正面(SGD)的備份算法。 SGD公司還將多次進行培訓樣本。 但與IRLS不同，SGD模型系數是受控的，因此迭代間的差總是以指數方式減小。 同樣，當系數差低於1.0e-6或100,000道次時，SGD將終止。 IRLS故障和SGD的參與將記錄在跟蹤日誌中。

對於這兩種算法，並非所有樣本都會進入模型訓練。 目前80%用於訓練模型。 訓練模型後，剩餘的20%樣本將用於根據混淆矩陣計算的準確度、召回率和精確度來評估模型強度。 越接近100%，得分模式就越好。
