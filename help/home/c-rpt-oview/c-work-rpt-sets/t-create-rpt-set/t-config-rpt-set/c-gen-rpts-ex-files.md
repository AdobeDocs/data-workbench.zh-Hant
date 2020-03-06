---
description: 以Excel檔案產生報表的資訊。
solution: Analytics
title: 以Microsoft Excel檔案產生報表
topic: Data workbench
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# 以Microsoft Excel檔案產生報表{#generating-reports-as-microsoft-excel-files}

以Excel檔案產生報表的資訊。

必須符合下列要求：

* Microsoft Excel必須安裝在與相同的機器上 [!DNL Report Server]。
* 執行此程式的使 [!DNL Report Server] 用者帳戶必須擁有存取Microsoft Excel的權限。

   >[!NOTE]
   >
   >
   >    
   >    
   >    * 當您以Excel檔案產生報表時，會開啟新的Excel例項。 如需此程式的詳細資訊，請參閱 [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。
   >    * 雖然資料工作台支援超過256欄和65,536列資料，但Microsoft Excel不支援。


如果符合這些要求， [!DNL Report Server] 會自動啟動Microsoft Excel，並從特定視覺化、維度和值圖例以及文字註解輸出資料至新的Excel活頁簿，每個工作表只有一個視覺化。

>[!NOTE]
>
>資料不會從圖形、路徑瀏覽器、程式地圖、散布圖和欄匯出。

除非您已指定 [!DNL Custom Title] 視覺化，否則會使用視窗類型（例如「影片表格」）作為工作表名稱。

如需指定視覺化的詳 [!DNL Custom Titles] 細資訊，請參閱資 [料工作台使用手冊](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html)。

## 使用範本檔案 {#section-40ab11916f464b1a88214ab969da6751}

您也可以使用範本Excel（或）檔案，將報表產生 [!DNL .xls] 為Excel [!DNL .xlsx]檔案。 使用範本檔案可以減少每次產生報表時您花在格式化資料上的時間。

此範本檔案必須是 [!DNL .xls] 或 [!DNL .xlsx] 檔案，而非 [!DNL .xlt] 檔案。

您可以選擇為每個個別報表定義範本、所有報表的通用範本，或兩者的組合。 這兩個項目不是互斥的，因此您可以定義一般範本，然後也可以定義特定範本。

若要使用您用於所有報表的一般範本產生報表，您必須在報表集檔案的「預設Excel範本」參數中指定該Excel檔案的名稱，然後將範本檔案放置在該報表集的相同資料夾中( [!DNL Report.cfg] data workbench installation directory [!DNL Report.cfg]**\*ProfileName*\Reports\*ReportSetName*)。 如需此參數的詳細資訊，請參 [閱Report.cfg參數](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

若要使用報表專用的範本產生報表，您必須將Excel檔案命名為與報表工作區( [!DNL .vw])檔案相同的檔案，然後將範本檔案放置在與報表工作區( [!DNL .vw])檔案相同的檔案夾中。

產生報表時，範本中現有的標籤式工作表（每個代表一個視覺化）會重新填入報表的最新資料，而任何未在範本中顯示為標籤式工作表的新視窗則會被忽略。 模板檔案中的任何其他頁籤式工作表都保持不變。

此外，如果您在範本Excel檔案中定義了要在產生報表時自動執行的巨集，請將巨集命名為&quot;VSExport&quot;。
