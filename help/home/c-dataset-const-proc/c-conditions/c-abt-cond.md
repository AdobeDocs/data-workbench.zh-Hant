---
description: 轉換和維使用條件來確定某些指示或操作何時應用於日誌欄位。
title: 關於條件
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# 關於條件{#about-conditions}

{{eol}}

轉換和維使用條件來確定某些指示或操作何時應用於日誌欄位。

「記錄項目條件」參數會使用條件來判斷資料集建構程式中應包含的記錄項目。 本附錄說明Data Workbench伺服器中可用的不同條件類型。

條件分為兩類：

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression]，和 [!DNL String Match] 條件可用來測試可用記錄欄位中的不同狀態。

* **[!DNL Boolean Operations]:** 此 [!DNL And], [!DNL Or]，和 [!DNL Neither] 條件可用來結合上述的測試操作。 例如，如果您有 [!DNL Range] 條件和 [!DNL String Match] 若要採取適當動作，您會將這兩個操作的子項設為 [!DNL Neither] 條件。 請注意， [!DNL And] 條件是系統中所有條件測試的根。
