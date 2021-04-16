---
description: 有關解決Web伺服器問題的資訊，例如，如果Web伺服器不旋轉，或者Web伺服器出現故障。
title: 瞭解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# 瞭解原因{#understanding-the-causes}

有關解決Web伺服器問題的資訊，例如，如果Web伺服器不旋轉，或者Web伺服器出現故障。

## 當Web伺服器退出旋轉{#section-b9f709099cb44b4f9d1acb38ca5330e3}時

當Web伺服器從伺服器池中轉出，但與傳送週期性心率的傳送器連接時，「截止時間」會維持在最新狀態，而不需要任何人介入。

## 當Web伺服器失敗{#section-19280cf83ca44bd7b1ee11bfc74494d2}

當Web伺服器因某些災難性故障而完全離線，或者未發送資料或心率時，[!DNL data workbench server]上的截止時間將停止，以保證它代表[!DNL data workbench server]上次從所知的所有資料源接收資料的時間。 系統本身會繼續處理資料，但[!DNL data workbench server]中以「開始時間」為基礎的任何資料，在Data Workbench中仍可供分析。 例如，「截止時間」會觸發報告，用於在系統中建立許多衍生維度。 當「截止時間」停止時，不會觸發報告，且這些特定衍生維度無法使用。

例如，如果WEB2在6月15日離線，而且5天內未傳送任何資料，則截止時間會是6月15日的某個時間。 例如，「昨天」的維度是6月14日，即使今天的日期是6月20日。
