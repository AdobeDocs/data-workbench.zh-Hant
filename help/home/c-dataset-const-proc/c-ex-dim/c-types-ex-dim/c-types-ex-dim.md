---
description: Insight Server可讓您定義可計數、簡單、多對多、數值、非正規和時間維度，以便納入資料集。
solution: Analytics
title: 擴展尺寸類型
topic: Data workbench
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 擴展尺寸類型{#types-of-extended-dimensions}

Insight Server可讓您定義可計數、簡單、多對多、數值、非正規和時間維度，以便納入資料集。

每個維度類型都有一組參數，您可編輯這些參數的值，以提供特定指示，讓Insight Server在資料集建構的轉換階段建立維度。

雖然某些參數不同於維類型，但所有參數都需要父維的規範（父參數）。 父級維決定哪些日誌源日誌條目作為新維的輸入提供。 換言之，在套用任何篩選前，與父維度元素關聯的記錄項目是與新維度關聯的項目。 父維還確定新維在資料集的層次中的位置，稱為資料集架構。 有關顯示資料集模式的介面的資訊，請參 [閱資料集配置工具](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

在Insight Server使用父級維度來決定在建立維度時應考慮哪些記錄項目後，它會套用指定的條件（條件參數）以空白不符合條件的記錄項目。 然後，伺服器為每個日誌條目標識指定輸入欄位（輸入參數）的值，並應用指定的操作（操作參數）（如果適用）。

>[!NOTE]
>
>如果日誌條目不滿足擴展維的條件，Insight Server將替換日誌條目中所有欄位的空值。 實際日誌條目仍然存在，而指定的操作將確定是否使用欄位 [!DNL Input] 的空白值。

