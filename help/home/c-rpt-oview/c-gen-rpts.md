---
description: 透過處理工作區並指定為報表，產生報表。
solution: Analytics
title: 產生報表
topic: Data workbench
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 產生報表{#generating-reports}

透過處理工作區並指定為報表，產生報表。

[!DNL Report] 根據其他檔案設定，以 [!DNL Every] 檔案 [!DNL Report.cfg] ( [!DNL "day]例如，每日處理報表的參數)中設定的間隔產生報 [!DNL Report.cfg] 表。

產生報表時，該報表的縮圖下方會顯示完 [!DNL Reports] 成百分比。 如果 [!DNL Report] 在產生報表時遇到問題，報表集資料夾的標籤上會 [!DNL Reports] 顯示最新的錯誤訊息。 如果 [!DNL Report] 某個特定報表確實發生錯誤，它會繼續處理該集中的其他報表。

您可以使用檔案中的參數，以下列任何或所有格式在報表集中產生 [!DNL Report Types] 報表 [!DNL Report.cfg] :

* Microsoft Excel檔案( [!DNL .xls] 或 [!DNL .xlsx])
* 可攜式網路圖形檔( [!DNL .png])
* 縮圖( [!DNL .jpg])

除了指定的輸出類型外，還 [!DNL Report] 會建立 [!DNL .xml] 與報表相同的檔案。 此 *`<report name>`*.xml檔案包含報表縮圖下方標籤上「資料工作台」中 [!DNL Reports] 所顯示報表的說明。 這可讓描述在透過報告入口網站分發報告時使用。 如需有關的資訊，請 [!DNL Report Portal]參閱使 [用報表入口網站](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>如果您重新定義內部量度，系統會因為值錯誤而意外運作。 除非量度讀取100%，否則您的報表不會產生。 建議您不要變更量度定義。
