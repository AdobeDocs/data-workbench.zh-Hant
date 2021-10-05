---
description: 以Excel檔案產生報表的資訊。
title: 以 Microsoft Excel 檔案產生報表
uuid: 0717a916-93d6-4b8e-a2ff-e9179ba4a66e
exl-id: 4e644867-db5e-4ca9-a2bf-1193e031f2bf
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 4%

---

# 以 Microsoft Excel 檔案產生報表{#generating-reports-as-microsoft-excel-files}

以Excel檔案產生報表的資訊。

必須符合下列要求：

* Microsoft Excel必須安裝在與[!DNL Report Server]相同的電腦上。
* 執行[!DNL Report Server]程式的使用者帳戶必須擁有存取Microsoft Excel的權限。

   >[!NOTE]
   >
   >
   >
   >
   >    * 以Excel檔案產生報表時，會開啟新的Excel例項。 有關此過程的詳細資訊，請參閱[https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757)。
   >    * 雖然Data Workbench支援超過256欄和65,536列的資料，但Microsoft Excel不支援。


如果符合這些要求，[!DNL Report Server]會自動啟動Microsoft Excel，並將特定視覺效果、維度和值圖例、文字註解的資料輸出至新Excel活頁簿，每個工作表各顯示一個視覺效果。

>[!NOTE]
>
>資料不會從圖形、路徑瀏覽器、程式圖、散布圖和地球表匯出。

除非您已為視覺效果指定[!DNL Custom Title]，否則會使用視窗類型（例如，電影表格）作為工作表名稱。

有關為視覺效果指定[!DNL Custom Titles]的詳細資訊，請參閱[Data Workbench用戶端指南](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html)。

## 使用範本檔案 {#section-40ab11916f464b1a88214ab969da6751}

您也可以使用範本Excel（[!DNL .xls]或[!DNL .xlsx]）檔案，以Excel檔案的形式產生報表。 使用範本檔案可減少每次產生報表時，您花在格式化資料上的時間。

此模板檔案必須是[!DNL .xls]或[!DNL .xlsx]檔案，而不是[!DNL .xlt]檔案。

您可以選擇為每個個別報表定義範本、為所有報表定義一般範本，或將兩者結合。 這兩個項目不互斥，因此您可以定義一般範本，然後也定義特定範本。

若要使用您用於所有報表的通用範本產生報表，您必須在該報表集檔案的[!DNL Report.cfg]中的「預設Excel範本」參數中指定該Excel檔案的名稱，然後將範本檔案放置在該報表集的[!DNL Report.cfg]資料夾中(*data workbench安裝目錄*\*ProfileName*\Reports\*ReportSetName*)。 如需此參數的相關資訊，請參閱[Report.cfg參數](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。

若要使用報表專用的範本產生報表，您必須將Excel檔案命名為與報表工作區相同的檔案([!DNL .vw])，然後將範本檔案放置在與報表工作區相同的資料夾中([!DNL .vw])。

產生報表時，範本中的現有標籤頁面（每個都代表一個視覺效果）會重新填入報表的最新資料，而範本中未以標籤頁面形式顯示的任何新視窗則會遭到忽略。 模板檔案中的任何其他頁簽頁都保持不變。

此外，如果您在範本Excel檔案中定義了要在產生報表時自動執行的巨集，請將巨集命名為「VSExport」。
