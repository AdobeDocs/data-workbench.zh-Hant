---
description: 處理工作區並將其指定為報表，借此產生報表。
title: 產生報表
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# 產生報表{#generating-reports}

處理工作區並將其指定為報表，借此產生報表。

[!DNL Report] 會根據檔案中參數所設 [!DNL Every] 定的間隔( [!DNL Report.cfg] 例如， [!DNL "day]」每日處理報表)，並根據其他檔案設 [!DNL Report.cfg] 定產生報表。

產生報表時，完成百分比會顯示在該特定報表縮圖的[!DNL Reports]標籤下。 如果[!DNL Report]在報表產生期間遇到問題，最新的錯誤訊息會顯示在報表集資料夾的[!DNL Reports]標籤上。 如果[!DNL Report]遇到特定報表的錯誤，則會繼續處理該集中的其他報表。

您可以使用[!DNL Report.cfg]檔案中的[!DNL Report Types]參數，以下列任何或所有格式在報表集中生成報表：

* Microsoft Excel檔案（[!DNL .xls]或[!DNL .xlsx]）
* 可移植網路圖形檔案([!DNL .png])
* 縮圖([!DNL .jpg])

[!DNL Report]會建立與報表同名的[!DNL .xml]檔案，並指定輸出類型。 此&#x200B;*`<report name>`*.xml檔案包含報表縮圖下方[!DNL Reports]標籤上Data Workbench顯示之報表的說明。 這可讓您在透過報表入口網站發佈報表時使用說明。 有關[!DNL Report Portal]的資訊，請參閱[使用Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)。

>[!NOTE]
>
>如果重新定義內部量度，系統會因錯誤值而意外運作。 量度讀取須達 100% 才會產生報告。建議您不要變更量度定義。
