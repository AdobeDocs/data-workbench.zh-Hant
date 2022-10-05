---
description: 在Report Portal中，您可以以Excel檔案(.xls或.xlsx)或.png檔案的形式檢視Report Server產生的報表。
title: 設定 Report.cfg 檔案
uuid: b6ce1621-283f-458d-a88d-a062539d243b
exl-id: 5af5abaa-77bf-447b-b341-8f44e228f37a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 4%

---

# 設定 Report.cfg 檔案{#configuring-report-cfg-files}

{{eol}}

在Report Portal中，您可以以Excel檔案(.xls或.xlsx)或.png檔案的形式檢視Report Server產生的報表。

若要在 [!DNL Report Portal]，您必須在 [!DNL Report.cfg] 檔案：

* 在 **[!UICONTROL Output Root]** 參數，指定用於入口的web伺服器的文檔根目錄。
* 在 **[!UICONTROL Report Types]** 參數，指定Excel、png和/或縮圖作為您要產生的報表類型。

當 [!DNL Report Server] 會以您指定的格式生成報告，並將這些檔案置於web伺服器的文檔根中，在安裝過程中，您可在此位置配置 [!DNL Report Portal] 來存取報表。

如需特定 [!DNL Report.cfg] 參數，請參閱 [Report.cfg參數](../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
