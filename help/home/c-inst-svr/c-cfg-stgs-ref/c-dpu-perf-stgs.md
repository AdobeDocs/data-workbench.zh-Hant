---
description: 調整DPU效能的指示。
title: DPU 效能設定
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 7%

---

# DPU 效能設定{#dpu-performance-settings}

{{eol}}

調整DPU效能的指示。

在*中完成下列參數 [!DNL Insight Server] 安裝目錄*\元件\DPU.cfg檔案。

| 參數 | 說明 |
|---|---|
| 執行批次計數 | 這是調諧參數。 預設值為 65536。您可以指定任意小的執行批計數。 對此值進行任何更改之前，請與Adobe聯繫。 |
| 執行批 | 這是調諧參數。 預設值為 128。對此值進行任何更改之前，請與Adobe聯繫。 |
| 執行時間 | 這是調諧參數。 預設值為0.100。請在對此值進行任何更改之前與Adobe聯繫。 |
| 錯誤時欄位轉儲 | 此參數可設為true或false。 若設為true, [!DNL Insight Server] 建立名為的檔案 [!DNL Field Dump number.txt] 執行引擎錯誤時，在其追蹤目錄中。 此 [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] 對疑難排解很實用。 |
| 設定檔路徑 | 儲存所有設定檔檔案的位置。 預設位置為Profiles\。 |
| 查詢記憶體限制 | 記憶體量（以位元組為單位） [!DNL Insight Server] 保留以儲存查詢結果。 預設值為100000000(100MB)。 如果查詢結果需要更多空間（例如，允許更多同時使用者），則可增加設定，但您必須繼續檢查 [!DNL Insight Server’s] 記憶體負載。 |
| 狀態路徑 | 系統狀態檔案的位置。 預設位置為「狀態」。 |
| 線程 | 適用於 [!DNL Insight Server] 具有多個處理器的電腦。 一般而言，對於任何n核系統，此值應設為n。預設值為1。 |
| 使用者路徑 | 授權用戶檔案的位置。 預設位置為「用戶」。 |
