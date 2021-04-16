---
description: 在報表入口網站中，您可以將報表伺服器產生的報表檢視為Excel檔案（.xls或。xlsx）或。png檔案。
title: 設定 Report.cfg 檔案
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# 設定 Report.cfg 檔案{#configuring-report-cfg-files}

在報表入口網站中，您可以將報表伺服器產生的報表檢視為Excel檔案（.xls或。xlsx）或。png檔案。

若要在[!DNL Report Portal]中顯示報表集，您必須在該報表集的[!DNL Report.cfg]檔案中設定下列參數：

* 在&#x200B;**[!UICONTROL Output Root]**&#x200B;參數中，指定用於入口網站的Web伺服器的檔案根目錄。
* 在&#x200B;**[!UICONTROL Report Types]**&#x200B;參數中，指定Excel、png和／或縮圖作為您要產生的報表類型。

當[!DNL Report Server]以您指定的格式產生報表時，會將這些檔案置於Web伺服器的檔案根目錄中，您在安裝期間會設定[!DNL Report Portal]以存取報表。

如需特定[!DNL Report.cfg]參數的詳細資訊，請參閱[Report.cfg參數](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)。
