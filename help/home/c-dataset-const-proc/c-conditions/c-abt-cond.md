---
description: 轉換和維使用條件來確定某些指令或操作何時適用於日誌欄位。
solution: Analytics
title: 關於條件
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 關於條件{#about-conditions}

轉換和維使用條件來確定某些指令或操作何時適用於日誌欄位。

「日誌條目條件」參數使用條件來確定資料集構建過程中應包括哪些日誌條目。 本附錄說明資料工作台伺服器中可用的各種條件類型。

條件可分為兩類：

* **[!DNL Test Operations]:**[!DNL Compare]、[!DNL Not Empty]、 、[!DNL Range][!DNL Regular Expression][!DNL String Match]、和條件用於測試可用日誌欄位中的不同狀態。

* **[!DNL Boolean Operations]:**使[!DNL And]用、[!DNL Or]和[!DNL Neither]條件來結合上述測試操作。 例如，如果您有條[!DNL Range]件和條件[!DNL String Match]必須同時為false才能採取適當的動作，則您會讓這兩個操作子項為該條[!DNL Neither]件。 請注意，[!DNL And]該條件是系統中所有條件測試的根。

