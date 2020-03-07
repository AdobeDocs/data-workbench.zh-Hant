---
description: 請依照下列步驟升級至Data Workbench v6.5。
title: 將6.4升級至6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Upgrading 6.4 to 6.5{#upgrading-to}

請依照下列步驟升級至Data Workbench v6.5。

## 升級需求與建議 {#section-8704a9ac358246cd81233dd0982d534f}

升級至資料工作台6.5時，請遵循這些需求和建議。

* 檔案中的 **[!DNL Components for Processing Servers\Communications.cfg]** 變更需要您更新DWB 6.5版本的此檔案。 已 *移除SourceListServer*、 *SegmentExportServer*&#x200B;和 *NormalizeServer* 項目。 (DPU不應執行原始碼清單 *、*&#x200B;區段匯出 *，或*&#x200B;標準化伺服器 **。)

* 關聯和弦、關聯矩陣、關聯和弦、關聯矩陣、傾向分數和最佳符合歸因視覺化現在為多遍視覺化。

   當工作區中有多個多重傳遞視覺化時，報表伺服器將無法依預設產生報表，並出現錯誤：

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   更新檔案或將此行新 [!DNL ReportServer.cfg] 增至「報告」區段中的現有檔案，以避免此 *錯誤* 。

   ```
   Max Multipass Per Slice = int: n
   ```

   其中n是工作區中「報表伺服器」支援的最大多次傳遞視覺化數目。

