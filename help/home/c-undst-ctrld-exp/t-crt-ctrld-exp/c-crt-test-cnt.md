---
description: 設定實驗之前，您應先建立要在實驗中使用的替代內容。
solution: Analytics
title: 建立測試內容
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# 建立測試內容{#creating-the-test-content}

{{eol}}

設定實驗之前，您應先建立要在實驗中使用的替代內容。

控制組將發送到原始URI，而測試組將發送到新的替代URI。

為避免混淆，請勿重複使用測試組檔案名。 例如，如果您使用名為的測試群組檔案執行實驗 [!DNL test2.asp]，不使用 [!DNL test2.asp] 作為下一個實驗中測試檔案的名稱。

假設在首頁上移動「請求示範」圖形連結會影響訪客轉換，我們會在新位置建立包含「請求示範」圖形連結的替代首頁。 以下部分說明如何指定控制組URI [!DNL index.asp] 替換為測試組URI [!DNL index2.asp] 特定百分比的訪客。
