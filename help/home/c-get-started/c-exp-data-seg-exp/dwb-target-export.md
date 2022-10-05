---
description: 使用TargetBulkUpload.exe ，從詳細資料表匯出Data Workbench資料至Adobe Target。
title: 匯出至 Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---

# 匯出至 Adobe Target{#export-to-adobe-target}

{{eol}}

使用TargetBulkUpload.exe ，從詳細資料表匯出Data Workbench資料至Adobe Target。

Data Workbench可讓您匯出檔案，以與Adobe Target整合為Adobe Experience Cloud的一部分。

此 **[!DNL TargetBulkUpload]** 在中找到檔案 *伺服器\指令碼* 資料夾。 執行檔具有重試邏輯以及用於優化效能的附加邏輯。

您可以修改 `TargetBulkUpload.cfg` 將檔案移至 *伺服器/管理員/匯出* 資料夾。 例如，您可以將「逾時間隔上限」設為720分鐘（預設值），以在指定時段後將上傳逾時。

**運作方式**

資料成功傳送至Target後，會持續監控上傳的狀態。 如果上傳成功，會記錄成功訊息。 如果上傳失敗或擱置中，監控會繼續。 您可以在 `TargetBulkUpload.cfg` 檔案。 如果上傳卡在Target，則會記錄訊息，且仍可監控狀態。

在觸發匯出的追蹤中，有兩個記錄檔產生於 [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

此 `targetbulkuploadexportname.log` 檔案具有多個批次的所有記錄的詳細狀態、要轉到的邊緣伺服器，以及狀態（成功、失敗、找不到配置檔案、狀態未知和卡住）。 如果發現任何批卡住，則不再處理該批。 停滯的批次URL可用於追蹤狀態。 請參閱下列範例資料，來自 `targetbulkuploadexportname.log.completed` 檔案：

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

卡住狀態值會隨卡住批次總大小增加，而無論上傳成功或失敗的次數為何。 總列值也會以相同數量的停滯批次大小增加。

>[!NOTE]
>
>之前，DWB資料是使用 [!DNL ExportIntegration.exe]. 目前，只有MMP、CRS和S/FTP匯出項目會與此執行檔搭配使用。 Adobe Target整合現在使用 [!DNL TargetBulkUpload.exe] Data Workbench。
