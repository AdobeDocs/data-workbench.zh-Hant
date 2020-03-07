---
description: 「查詢字串分組」可讓您將大量欄位整合在一起。
title: 查詢字串分組
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 查詢字串分組{#query-string-grouping}

「查詢字串分組」可讓您將大量欄位整合在一起。

查詢字串群組是每個描述檔專屬的，但在轉換中運作良好，如本範例所示：

1. 通過添加自定義配置檔案( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg])，然後添加Transformation Type *BuildNameValuePair* 作為參數來建立要打包的對。

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. 通過添加自定義配置檔案( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]** )，然後將轉換類型ExtractNameValuePairs添加為參數，建立一個新檔案，將壓縮資料提取到希望使用的欄位中。

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## 其他用途 {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

如果您有許多欄位具有自訂evar、prop和變數，在記錄處理期間，您可以建立名稱值對來結合報表中的欄位。 例如，您可以將命名值配對建立在組合的欄位中，以減少檔 [!DNL tempDB] 案大小。

![](assets/query_string_grouping.png)
