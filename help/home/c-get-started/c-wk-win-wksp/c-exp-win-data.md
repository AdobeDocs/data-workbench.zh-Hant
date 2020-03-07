---
description: 您可以將特定視窗中的資料匯出至Excel檔案（.xls或。xlsx）或標籤分隔值檔案(.tsv)。
solution: Analytics
title: 匯出視窗資料
topic: Data workbench
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 匯出視窗資料{#export-window-data}

您可以將特定視窗中的資料匯出至Excel檔案（.xls或。xlsx）或標籤分隔值檔案(.tsv)。

資料不會從圖形、路徑瀏覽器、程式地圖、散布圖和欄匯出。

## 將視窗資料匯出至Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

若要將個別視窗資料匯出至Microsoft Excel，必須符合下列要求：

* Microsoft Excel必須與資料工作台安裝在相同的機器上。
* 執行資料工作台程式的使用者帳戶必須擁有存取Microsoft Excel的權限。
* 將資料匯出為Excel檔案時，您會開啟新的Excel例項。
* 雖然「資料工作台」支援超過256欄和65,536列的資料，但8.0之前的Microsoft Excel版本則否。

如果符合這些要求，資料工作台會在您選取功能表選項時自動啟動Microsoft Excel並將資料匯出至新的Excel活 **[!UICONTROL Export To Excel]** 頁簿。

**若要將視窗資料匯出至。xls或。xlsx檔案**

按一下右鍵窗口的上邊框，然後按一下 **[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**。

![](assets/mnu_window_TitleBar_Export.png)

Excel會開啟包含匯出資料的新活頁簿。 除非您已提供自訂標題（如下節所述），否則此活頁簿會使用上述範例中 [!DNL Export title] 的「日表」來命名。

## 套用自訂標題 {#section-2a6559df812a470685e43923b7b9024e}

如果您為視窗提供自訂標題（使用功能表上的欄位），資料工作台會將資料匯出至的工作表會使用此自訂標題來命名，而非使用欄位中的 [!DNL Custom title][!DNL Export][!DNL Export title] 標題（上例中的日表）。

**若要將自訂標題套用至視覺化**

1. 按一下右鍵窗口的頂部邊框，然後按一下字 **[!UICONTROL Custom title]** 段。
1. you

![](assets/mnu_window_TitleBar_Export.png)

將視覺化匯出至Excel時，包含此視窗資料的工作表會使用您指定的標題來命名，而非在欄位中的標 [!DNL Export title] 題。

## 將視窗資料匯出至TSV檔案 {#section-93c6b24f7338430aaf5a63b99b9489e8}

**要將窗口導出到。tsv檔案**

按一下右鍵窗口的上邊框，然後按一下 **[!UICONTROL Export]** > **[!UICONTROL Export TSV]**。

1. 將出 [!DNL Save Window] 現對話框。
1. 導覽至您要儲存檔案的目錄。 如有必要，請變更檔案名稱，然後按一下 **[!UICONTROL Save]**。

