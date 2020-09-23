---
description: 調整DPU效能的指示。
solution: Analytics
title: DPU 效能設定
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---


# DPU 效能設定{#dpu-performance-settings}

調整DPU效能的指示。

在*安裝目錄*\Components\DPU.cfg檔案中 [!DNL Insight Server] ，填妥下列參數。

| 參數 | 說明 |
|---|---|
| 執行批次計數 | 這是調諧參數。 預設值為 65536。您可以指定任意小的執行批次計數。 請先聯絡Adobe，再對此值進行任何變更。 |
| 執行批 | 這是調諧參數。 預設值為 128。請先聯絡Adobe，再對此值進行任何變更。 |
| 執行時間 | 這是調諧參數。 預設值為0.100。請先聯絡Adobe，再對此值進行任何變更。 |
| 錯誤時的欄位轉儲 | 此參數可設為true或false。 如果設定為true，則當 [!DNL Insight Server] 執行引擎出現錯 [!DNL Field Dump number.txt] 誤時，在其跟蹤目錄中建立名為的檔案。 &lt; [!DNL Field Dump] > [!DNL number]對 [!DNL .txt] 於疑難排解非常有用。 |
| 描述檔路徑 | 儲存所有描述檔檔案的位置。 預設位置為「描述檔」。 |
| 查詢記憶體限制 | 保留用於儲存查詢結果的內 [!DNL Insight Server] 存量（以位元組為單位）。 預設值為10000000(100MB)。 如果需要更多查詢結果空間（例如，允許更多同時使用者），則可以增加設定，但必須繼續檢查內 [!DNL Insight Server’s] 存載入。 |
| 狀態路徑 | 系統狀態檔案的位置。 預設位置為「狀態」。 |
| 線程 | 多處理器電腦的 [!DNL Insight Server] 效能調整參數。 通常，對於任何n核系統，此值應設定為n。預設值為1。 |
| 使用者路徑 | 授權使用者檔案的位置。 預設位置為「使用者」。 |

