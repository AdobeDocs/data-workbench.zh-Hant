---
description: 使用「詳細資料表」的TargetBulkUpload.exe，將資料工作台資料匯出至Adobe Target。
title: 匯出至Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 匯出至Adobe Target{#export-to-adobe-target}

使用「詳細資料表」的TargetBulkUpload.exe，將資料工作台資料匯出至Adobe Target。

資料工作台可讓您匯出檔案以與Adobe Target整合，做為整合Adobe Experience Cloud的一部分。

檔案 **[!DNL TargetBulkUpload]** 位於伺服器安 *裝檔案的Server\Scripts* 資料夾中。 執行檔具有重試邏輯以及用於優化效能的附加邏輯。

您可以修改檔 `TargetBulkUpload.cfg` 案，並在執行上 ** 傳指令碼前，將它移至「伺服器／管理員／匯出」檔案夾。 例如，您可以將「最大逾時間隔」設為720分鐘（預設值），以在指定時段後逾時上傳。

**工作過程**

資料成功傳送至Target後，會持續監控上傳狀態。 如果上傳成功，則會記錄成功訊息。 如果上傳失敗或擱置中，監控會繼續。 您可以在檔案中設定逾時間 `TargetBulkUpload.cfg` 隔。 如果上傳卡在Target，則會記錄訊息，而且仍可監控狀態。

在跟蹤中為觸發的導出生成了兩個日誌檔案，位於 [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

文 `targetbulkuploadexportname.log` 件具有多批記錄的詳細狀態、要訪問的邊緣伺服器以及狀態（成功、失敗、找不到配置檔案、狀態未知和卡住）。 如果發現任何批被卡住，則不再處理該批。 滯留的批次URL可用於追蹤狀態。 請參閱檔案中的下列範例資 `targetbulkuploadexportname.log.completed` 料：

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

卡住狀態值隨卡住批次總大小增加，不論成功或失敗的上載數。 總行值也以相同數量的卡滯批大小遞增。

>[!NOTE]
>
>以前，DWB資料是使用導出的 [!DNL ExportIntegration.exe]。 目前，只有MMP、CRS和S/FTP匯出可與此可執行檔搭配使用。 Adobe Target整合現在使用「資料工 [!DNL TargetBulkUpload.exe] 作台」中的。

