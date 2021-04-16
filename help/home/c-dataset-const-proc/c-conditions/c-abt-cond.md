---
description: 轉換和維使用條件來確定某些指令或操作何時適用於日誌欄位。
title: 關於條件
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# 關於條件{#about-conditions}

轉換和維使用條件來確定某些指令或操作何時適用於日誌欄位。

「日誌條目條件」參數使用條件來確定資料集構建過程中應包括哪些日誌條目。 本附錄說明資料工作台伺服器中可用的各種條件類型。

條件可分為兩類：

* **[!DNL Test Operations]:** [!DNL Compare]、 [!DNL Not Empty]、 [!DNL Range]、和條 [!DNL Regular Expression]件用於測 [!DNL String Match] 試可用日誌欄位中的不同狀態。

* **[!DNL Boolean Operations]:** 使用 [!DNL And]、 [!DNL Or]和條 [!DNL Neither] 件來組合上述測試操作。例如，如果您有[!DNL Range]條件和[!DNL String Match]條件必須同時為false才能採取適當的動作，則您會將這兩個操作子項設為[!DNL Neither]條件。 請注意，[!DNL And]條件是系統中所有條件測試的根。
