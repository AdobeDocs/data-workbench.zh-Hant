---
description: 透過處理工作區並指定為報表，產生報表。
title: 產生報表
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# 產生報表{#generating-reports}

透過處理工作區並指定為報表，產生報表。

[!DNL Report] 根據其他檔案設定，以 [!DNL Every] 檔案中 [!DNL Report.cfg] 參數( [!DNL "day]例如，每日處理報表)中設定的間隔產生 [!DNL Report.cfg] 報表。

產生報表時，完成百分比會顯示在該特定報表縮圖下的[!DNL Reports]標籤上。 如果[!DNL Report]在產生報表時遇到問題，報表集資料夾的[!DNL Reports]標籤上會顯示最新的錯誤訊息。 如果[!DNL Report]遇到特定報表的錯誤，它會繼續處理該集中的其他報表。

您可以使用[!DNL Report.cfg]檔案中的[!DNL Report Types]參數，以下列任何或所有格式產生報表集：

* Microsoft Excel檔案（[!DNL .xls]或[!DNL .xlsx]）
* 可移植網路圖形檔案([!DNL .png])
* 縮圖([!DNL .jpg])

除了指定的輸出類型外，[!DNL Report]還會建立與報表相同的[!DNL .xml]檔案。 此&#x200B;*`<report name>`*.xml檔案包含報表縮圖下方[!DNL Reports]標籤上Data Workbench顯示的報表說明。 這可讓描述在透過報告入口網站分發報告時使用。 如需[!DNL Report Portal]的詳細資訊，請參閱[使用報表入口網站](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>如果您重新定義內部量度，系統會因為值錯誤而意外運作。 量度讀取須達 100% 才會產生報告。建議您不要變更量度定義。
