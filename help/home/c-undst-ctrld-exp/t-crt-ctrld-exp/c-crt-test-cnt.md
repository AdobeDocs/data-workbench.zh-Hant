---
description: 在設定實驗之前，您應先建立要在實驗中使用的替代內容。
solution: Analytics,Analytics
title: 建立測試內容
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# 建立測試內容{#creating-the-test-content}

在設定實驗之前，您應先建立要在實驗中使用的替代內容。

控制組被發送到原始URI，而測試組被發送到新的備用URI。

為避免混淆，請勿重複使用測試群組檔案名稱。 例如，如果您使用名為[!DNL test2.asp]的測試群組檔案來執行實驗，請勿使用[!DNL test2.asp]作為下個實驗中測試檔案的名稱。

若假設在首頁上移動「請求展示」圖形連結會影響「訪客轉換」，我們會在新位置建立包含「請求展示」圖形連結的替代首頁。 以下章節說明如何針對特定百分比的訪客，指定控制群組URI [!DNL index.asp]被測試群組URI [!DNL index2.asp]取代。
