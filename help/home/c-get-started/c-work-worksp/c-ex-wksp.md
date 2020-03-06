---
description: 您可以將工作區匯出為。png影像檔案，或將資料從特定視窗匯出至Excel（.xls或。xlsx）檔案。
solution: Analytics
title: 匯出工作區
topic: Data workbench
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 匯出工作區{#export-a-workspace}

您可以將工作區匯出為。png影像檔案，或將資料從特定視窗匯出至Excel（.xls或。xlsx）檔案。

## 將工作區匯出為PNG檔案 {#section-f9fbe0f0a1c341e2b063cce106cac35e}

可以以可移植網路圖形格式（檔案）保存工作區`.png` 的快照。 將工作區儲存為檔案時，可使用下列顏色 `.png` 選項：

* **黑色背景** ，會複製顯示的工作區。
* **白色背景** (White Background)會以彩色複製工作區的元素，並將它們顯示在白色背景上。
* **白色背景(B&amp;W)** ，以灰階方式複製工作區的元素，並在白色背景上顯示這些元素。

**若要將工作區匯出為。png檔案**

在工作區的標題列功能表中，按一下 **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*。

將出 [!UICONTROL Save Image As] 現對話框。

導覽至您要儲存檔案的目錄，視需要變更檔案名稱，然後按一下 **[!UICONTROL Save]**。

## 將工作區資料匯出至Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

將工作區匯出至Excel時，資料工作台會從特定視覺化、維度和值圖例以及文字註解匯出資料至新的Excel活頁簿，每個工作表只有一個視覺化。

若要將工作區和個別視窗匯出至Microsoft Excel，必須符合下列需求：

* Microsoft Excel必須與資料工作台安裝在相同的機器上。
* 執行資料工作台程式的使用者帳戶必須擁有存取Microsoft Excel的權限。

>[!NOTE]
>
>* 將資料匯出為Excel檔案時，您會開啟新的Excel例項。 如需此程式的詳細資訊，請參閱 [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。
>* 雖然「資料工作台」支援超過256欄和65,536列的資料，但8.0之前的Microsoft Excel版本則否。
>



如果符合這些要求，資料工作台會自動啟動Microsoft Excel，並將資料匯出至新的Excel活頁簿。 資料不會從下列視覺化匯出：圖形、路徑瀏覽器、流程地圖、散布圖和報表。

## 套用自訂標題 {#section-a332e157554546cb8e88922a8d7a4fa2}

除非您已在功能表上為視窗指定「自訂」標 [!UICONTROL Export] 題，否則 [!UICONTROL Export title] 會使用列出的（例如，城市表格）作為工作表名稱。

1. 按一下右鍵窗口的頂部邊框，然後按一下字 **[!UICONTROL Custom title]** 段。
1. 鍵入要應用於窗口的標題。

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>如果您在欄位中輸入連字型大小(-), [!UICONTROL Custom title] 此視覺化不會與工作區一起匯出。

將工作區匯出至Excel時，包含此視窗資料的工作表會使用您指定的標題來命名，而非在欄位中的標 [!UICONTROL Export title] 題。

## 將工作區或側欄匯出至Excel {#section-360438b66d5f4734826ab463b4a01a75}

**要將工作區資料導出到新檔案[!DNL .xls]或文[!DNL .xlsx]件**

1. 在工作區的標題列中，按一下 **[!UICONTROL Export]** > **[!UICONTROL Export]**。
1. 指定要匯出工作區、側欄還是兩者。

## 匯出至範本Excel檔案 {#section-814772929ca64cf6b92b89d3fdd02302}

您可以將工作區中的資料匯出至範本Excel檔案(`.xls` 或 `.xlsx`)。 使用範本檔案可以減少每次匯出工作區時，您花在格式化資料上的時間。

>[!NOTE]
>
>此範本檔案必須是 `.xls` 或 `.xlsx` 檔案，而非 `.xlt` 檔案。

匯出資料時，範本中現有的標籤式工作表（每個代表一個視覺化）會重新填入工作區的最新資料，而任何未以標籤式工作表形式出現在範本中的新視窗則會被忽略。 模板檔案中的任何其他頁籤式工作表都保持不變。

此外，如果您在範本Excel檔案中定義了要在產生報表時自動執行的巨集，請將巨集命名為&quot;VSExport&quot;。

假設您想要使用Excel檔案中另一個標籤式工作表上圓形圖中表格視覺化的匯出促銷活動資料，並想每週更新此資訊。 您可以使用範本，以便不必在每次要更新資料時，從表格的標籤表單重新建立參照至圓形圖的標籤表單。 表格資料會在匯出時更新，如此會自動更新圓形圖。

**要將工作區資料導出到模板或文[!DNL .xls]件，請執[!DNL .xlsx]行**

1. 以滑鼠右鍵按一下工作區的標題列，然後按一下 **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**。
1. 指定要匯出工作區、側欄還是兩者。

   對話框 [!UICONTROL Select a template worksheet] 隨即開啟。

1. 視需要完成下列步驟之一：

   * 如果您使用範本 `.xls` 檔案：

      1. 瀏覽並選擇範本 `.xls` 檔案。
      1. 按一下 **[!UICONTROL Open]**.
   * 如果您使用範本 `.xlsx` 檔案：

      1. 瀏覽至範本檔案的位置。 不 `.xlsx` 顯示檔案名。
      1. 在欄位中 [!UICONTROL File name] ，輸入並 `.xlsx` 按一下 **[!UICONTROL Open]**。 所有 `.xlsx` 檔案名都顯示在檔案清單中。

      1. 選擇模板 `.xlsx` 檔案。
      1. 按一下 **[!UICONTROL Open]**.


