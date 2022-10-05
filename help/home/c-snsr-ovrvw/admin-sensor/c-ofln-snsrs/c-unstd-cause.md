---
description: 有關解決Web伺服器問題的資訊，例如，如果Web伺服器被取出輪迴，或Web伺服器出現故障。
title: 瞭解原因
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# 瞭解原因{#understanding-the-causes}

{{eol}}

有關解決Web伺服器問題的資訊，例如，如果Web伺服器被取出輪迴，或Web伺服器出現故障。

## Web伺服器被取出時 {#section-b9f709099cb44b4f9d1acb38ca5330e3}

當從伺服器池中取出Web伺服器，但與發送週期性心率的發送器連接時，「截止」時間保持為最新，不需要對任何人進行干預。

## Web伺服器失敗時 {#section-19280cf83ca44bd7b1ee11bfc74494d2}

當Web伺服器因某些災難性故障而完全離線，或未傳送資料或心率時， [!DNL data workbench server] 停止保證代表 [!DNL data workbench server] 從所有資料源收到資料，而資料源是它所感知的。 系統本身會繼續處理資料，這仍可供Data Workbench分析，但 [!DNL data workbench server] 以「截止時間」為基礎無法運作。 例如，「截止時間」會觸發報表，用於在系統中建立許多衍生維度。 截止時間停止時，不會觸發報表，且這些特定衍生維度無法使用。

例如，如果WEB2在6月15日離線，且5天內未傳送任何資料，則截止時間會是6月15日的某個時間。 例如，「昨天」的維度會是6月14日，即使今天的日期是6月20日。
