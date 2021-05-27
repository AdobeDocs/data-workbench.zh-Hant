---
description: 您可以將某些視窗中的資料匯出至Excel檔案(.xls或.xlsx)或Tab分隔值檔案(.tsv)。
title: 匯出視窗資料
uuid: 71a93f35-1096-41ae-8808-e5b94813a52c
exl-id: ab931453-d366-4d3a-990e-7a368328da2d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 1%

---

# 匯出視窗資料{#export-window-data}

您可以將某些視窗中的資料匯出至Excel檔案(.xls或.xlsx)或Tab分隔值檔案(.tsv)。

資料不會從圖形、路徑瀏覽器、程式圖、散布圖和地球表匯出。

## 將窗口資料導出到Microsoft Excel {#section-b660adf7f4f64a2b9be7287c591b67b0}

若要將個別視窗資料匯出至Microsoft Excel，必須符合下列要求：

* Microsoft Excel必須安裝在與Data Workbench相同的電腦上。
* 運行Data Workbench進程的用戶帳戶必須具有訪問Microsoft Excel的權限。
* 將資料匯出為Excel檔案時，會開啟新的Excel例項。
* 雖然Data Workbench支援超過256列和65,536列資料，但8.0之前的Microsoft Excel版本則否。

如果滿足這些要求，當您選取&#x200B;**[!UICONTROL Export To Excel]**&#x200B;功能表選項時，Data Workbench會自動啟動Microsoft Excel並將資料匯出至新的Excel活頁簿。

**若要將視窗資料匯出為.xls或.xlsx檔案**

按一下右鍵窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export to Excel]**。

![](assets/mnu_window_TitleBar_Export.png)

Excel會開啟包含匯出資料的新活頁簿。 除非您已提供自訂標題（如下節所述），否則此活頁簿的名稱為使用[!DNL Export title]（上述範例中的日表格）。

## 應用自定義標題{#section-2a6559df812a470685e43923b7b9024e}

如果您提供視窗的自訂標題（使用[!DNL Export]功能表上的[!DNL Custom title]欄位），則系統會使用此自訂標題來命名Data Workbench匯出資料的工作表，而非使用[!DNL Export title]欄位中的標題（上述範例中的「日表格」）。

**若要將自訂標題套用至視覺效果**

1. 按一下右鍵窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Custom title]**&#x200B;欄位。
1. you

![](assets/mnu_window_TitleBar_Export.png)

將視覺效果匯出至Excel時，系統會使用您指定的標題（而非[!DNL Export title]欄位中的標題）命名包含此視窗資料的工作表。

## 將窗口資料導出到TSV檔案{#section-93c6b24f7338430aaf5a63b99b9489e8}

**要將窗口導出為.tsv檔案**

按一下右鍵窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export TSV]**。

1. 將出現[!DNL Save Window]對話框。
1. 導覽至您要儲存檔案的目錄。 如有必要，請更改檔案的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。
