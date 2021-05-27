---
description: 值設定檔量度
title: 值設定檔量度
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
exl-id: 9e95008c-1162-4f50-89d2-dcf5fcf8746a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 17%

---

# 值設定檔量度{#value-profile-metrics}

| 量度 | 公式 | 層級 | 說明 |
|---|---|---|---|
| 轉換 | `Sessions[not Session_Value=#0]/Sessions` | 工作階段 | 生成業務價值的會話的百分比（由業務價值模型定義）。 |
| 值百分比 | `Value/total(Value)` | 工作階段 | 從所選工作階段集產生的總值百分比。 |
| 值 | `sum(Session_Value, Session)*0.01` | 工作階段 | 生成的總業務價值，以美元（由業務價值模型定義）表示。 |
| 值事件 | `Sessions[not Session_Value=#0]` | 工作階段 | 生成業務價值的會話數（由業務價值模型定義）。 |
| 每位訪客的值事件 | `(Value_Events/Visitors) by Visitor` | 訪客 | 產生業務值的每個訪客的平均工作階段數（由業務值模型定義）。 |
| 每位訪客的值 | `(Value/Visitors) by Visitor` | 訪客 | 每位訪客產生的平均商業價值（以美元為單位）。 |
