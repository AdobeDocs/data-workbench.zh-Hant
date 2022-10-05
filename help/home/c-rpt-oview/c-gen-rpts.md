---
description: 處理工作區並將其指定為報表，借此產生報表。
title: 產生報表
uuid: 90bc42b3-d7f2-46f2-8c68-5c682d163f3c
exl-id: 8e5765e8-71b6-4716-96fe-5c7f69407295
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 9%

---

# 產生報表{#generating-reports}

{{eol}}

處理工作區並將其指定為報表，借此產生報表。

[!DNL Report] 會以 [!DNL Every] 參數 [!DNL Report.cfg] 檔案(例如 [!DNL "day]，」每日處理報表)，並以其他 [!DNL Report.cfg] 檔案設定。

產生報表時，完成百分比會顯示在 [!DNL Reports] 標籤。 若 [!DNL Report] 在產生報表時遇到問題，最新的錯誤訊息會顯示在 [!DNL Reports] 標籤。 若 [!DNL Report] 遇到特定報表的錯誤時，會繼續處理該集中的其他報表。

您可以使用 [!DNL Report Types] 參數 [!DNL Report.cfg] 檔案：

* Microsoft Excel檔案( [!DNL .xls] 或 [!DNL .xlsx])
* 可移植網路圖形檔案( [!DNL .png])
* 縮圖( [!DNL .jpg])

連同指定的輸出類型， [!DNL Report] 建立 [!DNL .xml] 檔案的名稱與報表相同。 此 *`<report name>`*.xml檔案包含Data Workbench上顯示的報表說明 [!DNL Reports] 標籤。 這可讓您在透過報表入口網站發佈報表時使用說明。 如需 [!DNL Report Portal]，請參閱 [使用Report Portal](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>如果重新定義內部量度，系統會因錯誤值而意外運作。 量度讀取須達 100% 才會產生報告。建議您不要變更量度定義。
