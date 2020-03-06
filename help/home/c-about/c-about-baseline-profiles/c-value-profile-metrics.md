---
description: 'null'
solution: Analytics
title: 值描述檔度量
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 值描述檔度量{#value-profile-metrics}

| 量度 | Formula | 層級 | 說明 |
|---|---|---|---|
| 轉換 | [!DNL會[話不是會話值=#0]/會話] | 作業階段 | 產生業務價值的會話的百分比（由業務價值模型定義）。 |
| 值百分比 | [!DNL Value/total(Value)] | 作業階段 | 從所選會話集生成的總值的百分比。 |
| 值 | [!DNL sum(Session_Value, Session)*0.01] | 作業階段 | 生成的總業務值（以美元表示）（由業務值模型定義）。 |
| 值事件 | [!DNL會[話不是會話值=#0]] | 作業階段 | 生成業務值的會話計數（由業務值模型定義）。 |
| 每個訪客的值事件 | [!DNL (Value_Events/Visitors) by Visitor] | 訪客 | 產生業務值的每位訪客的平均工作階段數（由業務值模型定義）。 |
| 每位訪客的值 | [!DNL (Value/Visitors) by Visitor] | 訪客 | 每位訪客產生的平均業務值（以美元為單位）。 |
