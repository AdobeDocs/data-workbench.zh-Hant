---
description: 查詢字串分組可讓您將大量欄位整合在一起。
title: 查詢字串分組
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# 查詢字串分組{#query-string-grouping}

{{eol}}

查詢字串分組可讓您將大量欄位整合在一起。

查詢字串分組是每個設定檔專屬的，但在轉換中運作良好，如以下範例所示：

1. 通過添加自定義配置檔案( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg])，然後添加轉換類型 *BuildNameValuePair* 作為參數。

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

1. 建立新檔案，借由新增自訂設定檔案( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg])，然後添加轉換類型 *ExtractNameValuePairs* 作為參數。

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

如果您有許多欄位具有自訂evar、prop和變數，則在記錄處理期間，您可以建立名稱值組來結合報表中的欄位。 例如，您可以將命名值配對建置到結合的欄位中，以減少 [!DNL tempDB] 檔案大小。

![](assets/query_string_grouping.png)
