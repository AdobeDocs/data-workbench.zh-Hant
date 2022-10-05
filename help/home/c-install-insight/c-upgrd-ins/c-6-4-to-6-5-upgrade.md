---
description: 請依照下列步驟升級至Data Workbenchv6.5。
title: 6.4 升級至 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
exl-id: bcfd1ab1-2fb8-4bcd-b6c9-329143274ca4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 2%

---

# 6.4 升級至 6.5{#upgrading-to}

{{eol}}

請依照下列步驟升級至Data Workbenchv6.5。

## 升級需求和Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

升級至Data Workbench6.5時，請遵循這些需求和建議。

* 變更 **[!DNL Components for Processing Servers\Communications.cfg]** 檔案會要求您為DWB 6.5版本更新此檔案。 此 *SourceListServer*, *SegmentExportServer*，和 *標準化伺服器* 項目已移除。 (DPU不應執行 *源精*, *區段匯出*，或 *標準化伺服器*.)

* 「關聯和諧」、「關聯矩陣」、「關聯和諧」、「關聯矩陣」、「傾向分數」和「最佳配適歸因」視覺效果現在為多遍視覺效果。

   工作區中有多個多遍視覺效果時，報表伺服器預設無法產生報表，並出現錯誤：

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   更新 [!DNL ReportServer.cfg] 檔案，或將此行新增至您現有的檔案 *報表* 區段。

   ```
   Max Multipass Per Slice = int: n
   ```

   其中n是工作區中報表伺服器支援的最大多遍視覺效果數。
