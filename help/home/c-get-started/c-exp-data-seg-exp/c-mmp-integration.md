---
description: 資料工作台可讓您匯出檔案，以與整合的Adobe Experience Cloud中的「設定檔與觀眾匯出」整合。
title: 主行銷設定檔匯出
uuid: bae0f0c5-a452-4afd-9f2c-5f3ab69a12d2
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 主行銷設定檔匯出{#master-marketing-profile-export}

資料工作台可讓您匯出檔案，以與Profiles和Audiences整合，成為整合Adobe Experience Cloud的一部分。

<!-- <a id="section_731922BC8628479198A41EF3EA72F2FF"></a> -->

Profiles and Audiences是 [Experience Cloud Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html)（Experience Cloud Identity Service的核心服務）的一部分 [!DNL Adobe Experience Cloud]。 「設定檔與觀眾」匯出可讓觀眾使用唯一的Experience Cloud ID(ECID)在Experience Cloud中共用，此ID會指派給每位訪客，然後由 [Audience Manager使用](https://docs.adobe.com/content/help/en/audience-manager/user-guide/aam-home.html)。 應用 [!DNL ExportIntegration.exe] 程式( [!DNL E:\Server\Scripts])可用來產生MMP和Adobe Target匯出。

**設定FSU伺服器以使用設定檔和觀眾**

1. 存取您的FSU伺服器。
1. 開啟MMPExport.cfg檔案。 `Server/Admin/Export/MMPExport.cfg`。
1. 在所有欄位中輸入值（視需要而定）。 例如：

   >[!NOTE]
   >
   >MMP/AAM整合依賴Amazon的s3資料傳輸桶。
   >
   >
   >MMP(s3)傳輸所需的s3資訊可從Audience Manager團隊取得。

   ```
   Sample MMPExport.cfg
   MMP Export Configuration = MMPExportConfiguration: 
   s3 Bucket = string: aws_bucket_for_mmp 
   s3 Object Directory = string: test/files/ 
   s3 Region = string: us-east-1 
   s3 Access Key = string: ZZKI62OO5YBA 
   s3 Secret Key = string: ioqwa3OpNE5 
   data Provider Name = string: 895 
   client ID = string: mcprofile2-test 
   client Secret = string: saea1287617212987q 
   username = string: mmptest 
   password = string: pass 
   numRecordsPerChunk = int:  
   numThreads = int:  
   maxRetriesOnSendFailure = unsigned int:
   ```

   >[!NOTE]
   >
   >此檔 [!DNL MMPExport.cfg]案也可讓您取用所有記錄、將其分割為一組，並建立多個記錄。 然後，這些記錄塊會匯出至Amazon S3。 建立記錄塊需要三個必需參數： [!DNL numRecordsPerChunk]、 [!DNL numThreads]和 [!DNL maxRetriesOnSendFailure]。

**參數定義**

<table id="table_DDEFBC45895A4663973F9C2EB9052FEF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 定義 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>s3儲存貯體</i> </td> 
   <td colname="col2"> 將導出轉移到的AWS S3儲存桶。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3物件目錄</i> </td> 
   <td colname="col2"> 儲存s3檔案的路徑。 這支援子目錄。 <p> <p>重要： 路徑中不允許空格和多位元組字元，並會在匯出時產生錯誤。 （允許使用hypen）。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3地區</i> </td> 
   <td colname="col2"> 將導出發送到的AWS s3地區。 例如 us-east-1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3訪問密鑰</i> </td> 
   <td colname="col2"> AWS s3訪問密鑰 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>s3密鑰</i> </td> 
   <td colname="col2"> AWS s3密鑰 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>資料提供者名稱</i> </td> 
   <td colname="col2"> 這將是分別用於儲存AAM中區段和特徵的資料夾名稱。 這應該是每位客戶的唯一值。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>用戶端ID</i> </td> 
   <td colname="col2"> 這是為MMP布建時提供給客戶的唯一客戶ID。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>用戶端密碼</i> </td> 
   <td colname="col2"> <p><i></i>這是為客戶布建MMP時提供給客戶的唯一客戶機密碼。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>username</i> </td> 
   <td colname="col2"> MMP用戶名 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>password</i> </td> 
   <td colname="col2"> MMP密碼 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numRecordsPerChunk</i> </td> 
   <td colname="col2"> <p>根據記錄數確定區塊大小。 </p> <p>實現將用戶指定的值剪輯為min = 1000 records&amp; nbsp;（~50 KB區塊）&amp; nbsp；和max = 50000記錄（~2.5 MB區塊）。&amp;nbsp；如果用戶未指定此配置屬性，則使用預設值10000。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>numThreads</i> </td> 
   <td colname="col2"> <p>確定塊發送部分的並行度。 它接受1到24個線程之間的值，其預設值為12個線程。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <i>maxRetriesOnSendFailure</i> </td> 
   <td colname="col2"> <p>確定在塊發送失敗時要進行的重試嘗試次數。 預設值為0，指定無重試次數。 </p> <p>兩次重試之間使用2秒的睡眠間隔。 </p> </td> 
  </tr> 
 </tbody> 
</table>

**從客戶端生成MMP導出**

1. 從用戶端開啟工作區，然後按一下滑鼠右 **[!UICONTROL Tools]**&#x200B;鍵> **[!UICONTROL Detail Table]**。
1. 添加 **級別**。
1. 按一下右鍵標題並選擇「添 **加屬性」**。
1. 以滑鼠右鍵按一下頁首，然後選 **取「新增主行銷描述檔匯出」**。 ![](assets/mmp_mmp_export.png)
1. 展開 **查詢**。

   ![](assets/mmp_mmp_query.png)

1. 展開 **MMP配置**。
1. （必要）輸入「 **MMP區段名稱** 」和「 **MMP訪客ID」欄位**。 這些參數不能留空。
1. 「 **MMP區段名稱** 」應符合MMP中定義的區段ID。
1. MMP訪 **客ID** 是步驟4中定義的屬性欄，與訪客 **ID對應**。
1. 在輸入這些欄位後，您可以以滑鼠右鍵按一下匯出的標題，然後選擇「另存 **為** &quot;User\.export&quot;，以儲存匯出。
1. 開啟「 **管理** >描述檔 **管理員** 」，並將匯出儲存至描述檔。

   如果所有資料都輸入正確，則會在FSU([!DNL Server/Exports])中生成導出檔案，並且還會使用中的資訊將導出傳輸到AWS [!DNL MMPExport.cfg]。 中提供了此日誌 [!DNL Server/Trace/]。 例如， [!DNL MMP-102014-133651- `<Segment Export Name>` .log]

```
Query = SegmentExportQuery: 
Command = string: ExportIntegration.exe 
Command Arguments = string: \"%file%.cfg\" \"%file%\" 
Filter = string: 
Level = string: Page View 
MMP Configuration = MMPConfiguration: 
MMP Segment Name = string: 12345 
MMP Visitor ID Field = string: Tracking ID 
Oneshot = bool: true 
Output Fields = vector: 3 items 
0 = ColumnDefinition: 
Column Name = string: 
Field Name = string: Tracking ID 
1 = ColumnDefinition: 
Column Name = string: 
Field Name = string: PID 
2 = ColumnDefinition: 
Column Name = string: 
Field Name = string: SID 
Output File = string: MMPTest.txt 
Output Format = string: %1%\t%2%\t%3%\r\n 
Schedule End Time = string: 
Schedule Every = string: 
Schedule Start Time = string: 
Time Limit (sec) = double: 1800 
```

| 配置詳細資訊 | 說明 |
|---|---|
| MMP區段ID | 必填.這是您在Audience Manager中先定義的識別碼。 |
| MMP訪客ID欄位 | 映射ECID。 |

