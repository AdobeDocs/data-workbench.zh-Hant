---
description: 為區段匯出檔案建立自訂欄匯出標頭，為匯出的區段新增容易理解的說明。 此匯出功能也可讓您輸出為TSV和CSV檔案。
title: 使用自訂標頭匯出區段
uuid: 186e7868-13b2-42e1-b83f-5a752ee9b407
exl-id: 1d27f926-35e1-4886-b7a6-702d9947dabb
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 4%

---

# 使用自訂標頭匯出區段{#segment-export-with-custom-headers}

{{eol}}

為區段匯出檔案建立自訂欄匯出標頭，為匯出的區段新增容易理解的說明。 此匯出功能也可讓您輸出為TSV和CSV檔案。

「區段匯出」已新增功能，包括以標題或CSV和TSV格式匯出的功能。

您可以為匯出檔案建立欄標題。

## 建立新區段匯出 {#section-cffff55855f8467ea468b71393ab7676}

1. 開啟工作區並按一下滑鼠右鍵 **[!UICONTROL Tools]** > **[!UICONTROL Detail Table]**.

1. 按一下滑鼠右鍵並選取 **[!UICONTROL Add Level > Extended]** >選擇項目。
1. 按一下右鍵標題並選擇 **[!UICONTROL Add Attribute.]** 從功能表中選取維度。

1. 按一下右鍵標題並選擇 **[!UICONTROL Add Metric.]** 從功能表中選取量度。

1. 按一下右鍵標題並選擇 **[!UICONTROL New Segment Export]**.

   ![](assets/segment_export_headers.png)

   **[!UICONTROL New Segment Export with Header]** 會以量度名稱自動填入欄名稱。 **[!UICONTROL New Segment Export]** 需要您設定自訂名稱。 ![](assets/segment_export_with_headers.png)

   >[!NOTE]
   >
   >「欄名稱」欄位不能留空，或標題不存在。

1. 以滑鼠右鍵按一下並命名區段，然後按一下 **[!UICONTROL Save Export File]**.

   將會開啟一個導出窗口。

1. 以滑鼠右鍵按一下匯出名稱，然後按一下 **另存新檔`<export filename>`**.

   ![](assets/segment_export_headers_7.png)

1. 按一下右鍵 [!DNL Admin] > [!DNL Profile Manager] > [!DNL Expand Export]. 找到您剛建立的匯出檔案，並將其儲存至現有設定檔。

   ![](assets/segment_export_headers_8.png)
