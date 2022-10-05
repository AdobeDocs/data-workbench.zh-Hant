---
description: Insight Server可讓您定義可數、簡單、多對多、數值、非正規及時間維度，以便納入您的資料集中。
title: 延伸維度類型
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# 延伸維度類型{#types-of-extended-dimensions}

{{eol}}

Insight Server可讓您定義可數、簡單、多對多、數值、非正規及時間維度，以便納入您的資料集中。

每個維度類型都有一組參數，您可以編輯這些參數的值，以提供特定指示，讓Insight Server在資料集建構的轉換階段建立維度。

雖然某些參數不同於維類型，但所有參數都需要父維的規範（父參數）。 父維確定將來自日誌源的日誌條目作為新維的輸入提供。 換言之，在套用任何篩選條件之前，與父維度的元素相關聯的記錄項目就是與新維度相關聯的項目。 父維度也會決定新維度在資料集階層中的位置，稱為資料集結構。 有關顯示資料集架構的介面的資訊，請參見 [資料集組態設定工具](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Insight Server使用父維度來決定建立維度時應考量哪些記錄項目後，會套用指定的條件（條件參數）以空白不符合條件的記錄項目。 然後，伺服器為每個日誌條目標識指定輸入欄位（輸入參數）的值，並應用指定的操作（操作參數）（如果適用）。

>[!NOTE]
>
>如果記錄項目不符合延伸維度的條件，Insight Server會替代記錄項目中所有欄位的空白值。 實際日誌條目仍然存在，而指定的操作將確定 [!DNL Input] 欄位。
