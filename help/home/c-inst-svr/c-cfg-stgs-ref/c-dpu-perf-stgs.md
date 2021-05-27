---
description: 調整DPU效能的指示。
title: DPU 效能設定
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---

# DPU 效能設定{#dpu-performance-settings}

調整DPU效能的指示。

在* [!DNL Insight Server]安裝目錄*\Components\DPU.cfg檔案中完成以下參數。

| 參數 | 說明 |
|---|---|
| 執行批次計數 | 這是調諧參數。 預設值為 65536。您可以指定任意小的執行批計數。 對此值進行任何更改之前，請與Adobe聯繫。 |
| 執行批 | 這是調諧參數。 預設值為 128。對此值進行任何更改之前，請與Adobe聯繫。 |
| 執行時間 | 這是調諧參數。 預設值為0.100。請在對此值進行任何更改之前與Adobe聯繫。 |
| 錯誤時欄位轉儲 | 此參數可設為true或false。 如果設為true，則每當執行引擎出錯時， [!DNL Insight Server]會在其跟蹤目錄中建立名為[!DNL Field Dump number.txt]的檔案。 [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt]對於疑難排解非常有用。 |
| 設定檔路徑 | 儲存所有設定檔檔案的位置。 預設位置為Profiles\。 |
| 查詢記憶體限制 | [!DNL Insight Server]保留用於儲存查詢結果的記憶體量（以位元組為單位）。 預設值為100000000(100MB)。 如果查詢結果需要更多空間（例如，允許更多同時用戶），則可以增加設定，但必須繼續檢查[!DNL Insight Server’s]記憶體負載。 |
| 狀態路徑 | 系統狀態檔案的位置。 預設位置為「狀態」。 |
| 線程 | 具有多個處理器的[!DNL Insight Server]電腦的效能調整參數。 一般而言，對於任何n核系統，此值應設為n。預設值為1。 |
| 使用者路徑 | 授權用戶檔案的位置。 預設位置為「用戶」。 |
