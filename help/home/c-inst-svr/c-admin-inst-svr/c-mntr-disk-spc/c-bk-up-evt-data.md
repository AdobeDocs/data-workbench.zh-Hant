---
description: 事件資料必須每天使用公司的常規備份系統和災難恢復過程進行備份。
title: 備份事件資料
uuid: 1b9e5dfe-0bf2-4ee9-bf70-1dd320a678d6
exl-id: 5afeb3a2-a2e7-4155-8fb9-1abc9c22c3c6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 5%

---

# 備份事件資料{#backing-up-event-data}

事件資料必須每天使用公司的常規備份系統和災難恢復過程進行備份。

**建議頻率：每** 日

[!DNL Insight Server] 每天12:00 GMT開始新的日誌檔案。Adobe建議您每天在格林尼治時間12:00 AM後不久備份日誌檔案，以便捕獲前一天的所有資料。 例如，在12月15日的12:05 GMT備份所有日誌檔案會捕獲12月14日的所有資料。 [!DNL Insight Server] 不需要在日誌檔案備份期間停止，所有功能都保持可用。

## 備份整合、作業系統、輸出和系統資料{#section-217e52a99f944d8e83a3cc98f3d06e7e}

**建議頻率：每** 日

必須使用貴公司正常的備份和災難恢復系統定期並認真備份整合、作業系統、輸出和系統資料。
