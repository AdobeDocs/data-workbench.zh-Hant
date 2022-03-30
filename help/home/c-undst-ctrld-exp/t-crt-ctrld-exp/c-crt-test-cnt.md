---
description: 在配置實驗之前，應建立要在實驗中使用的替代內容。
solution: Analytics
title: 建立測試內容
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# 建立測試內容{#creating-the-test-content}

在配置實驗之前，應建立要在實驗中使用的替代內容。

控制組被發送到原始URI，而test組被發送到新的備用URI。

為避免混淆，請勿重用test組檔案名。 例如，如果使用名為的test組檔案運行實驗 [!DNL test2.asp]，不使用 [!DNL test2.asp] 作為下一個實驗中test檔案的名稱。

如果假設在首頁上移動「請求演示」圖形連結會影響訪問者轉換，我們將在新位置建立包含「請求演示」圖形連結的備用首頁。 下節介紹如何指定控制組URI [!DNL index.asp] 替換為test組URI [!DNL index2.asp] 有一定比例的遊客。
