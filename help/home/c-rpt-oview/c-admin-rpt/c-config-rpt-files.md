---
description: 在報表入口網站中，您可以將報表伺服器產生的報表檢視為Excel檔案（.xls或。xlsx）或。png檔案。
solution: Analytics
title: 設定Report.cfg檔案
topic: Data workbench
uuid: b6ce1621-283f-458d-a88d-a062539d243b
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定Report.cfg檔案{#configuring-report-cfg-files}

在報表入口網站中，您可以將報表伺服器產生的報表檢視為Excel檔案（.xls或。xlsx）或。png檔案。

若要在中顯示報表集， [!DNL Report Portal]您必須在該報表集的檔案中 [!DNL Report.cfg] 設定下列參數：

* 在參數 **[!UICONTROL Output Root]** 中，指定用於入口網站的Web伺服器的檔案根目錄。
* 在參 **[!UICONTROL Report Types]** 數中，指定Excel、png和／或縮圖作為您要產生的報表類型。

當 [!DNL Report Server] 以您指定的格式產生報表時，會將這些檔案置於Web伺服器的檔案根目錄中，此為安裝期間您設定存取報表 [!DNL Report Portal] 的位置。

如需特定參數的詳細資 [!DNL Report.cfg] 訊，請參 [閱Report.cfg參數](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
