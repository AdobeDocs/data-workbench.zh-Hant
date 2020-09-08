---
description: 'null'
solution: Analytics
title: 值設定檔量度
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 16%

---


# 值設定檔量度{#value-profile-metrics}

| 量度 | 公式 | 層級 | 說明 |
|---|---|---|---|
| 轉換 | `Sessions[not Session_Value=#0]/Sessions` | 工作階段 | 產生業務價值的會話的百分比（由業務價值模型定義）。 |
| 值百分比 | `Value/total(Value)` | 工作階段 | 從所選會話集生成的總值的百分比。 |
| 值 | `sum(Session_Value, Session)*0.01` | 工作階段 | 生成的總業務值（以美元表示）（由業務值模型定義）。 |
| 值事件 | `Sessions[not Session_Value=#0]` | 工作階段 | 生成業務值的會話計數（由業務值模型定義）。 |
| 每個訪客的值事件 | `(Value_Events/Visitors) by Visitor` | 訪客 | 產生業務值的每位訪客的平均工作階段數（由業務值模型定義）。 |
| 每位訪客的值 | `(Value/Visitors) by Visitor` | 訪客 | 每位訪客產生的平均業務值（以美元為單位）。 |
