---
description: 有關解決Web伺服器問題的資訊，例如，如果Web伺服器不旋轉，或者Web伺服器出現故障。
solution: Analytics
title: 瞭解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---


# 瞭解原因{#understanding-the-causes}

有關解決Web伺服器問題的資訊，例如，如果Web伺服器不旋轉，或者Web伺服器出現故障。

## 當Web伺服器退出輪轉時 {#section-b9f709099cb44b4f9d1acb38ca5330e3}

當Web伺服器從伺服器池中轉出，但與傳送週期性心率的傳送器連接時，「截止時間」會維持在最新狀態，而不需要任何人介入。

## 當Web伺服器出現故障時 {#section-19280cf83ca44bd7b1ee11bfc74494d2}

當Web伺服器因為發生災難性故障而完全離線，或未傳送資料或心率時，「截止時間」會停止，以保證它代表上次從 [!DNL data workbench server][!DNL data workbench server] ALL資料來源收到的資料。 系統本身會繼續處理資料，但資料工作台中仍可供分析，但以「截止時間」為基 [!DNL data workbench server] 礎的任何資料都無法運作。 例如，「截止時間」會觸發報告，用於在系統中建立許多衍生維度。 當「截止時間」停止時，不會觸發報告，且這些特定衍生維度無法使用。

例如，如果WEB2在6月15日離線，而且5天內未傳送任何資料，則截止時間會是6月15日的某個時間。 例如，「昨天」的維度是6月14日，即使今天的日期是6月20日。
