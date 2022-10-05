---
description: 您可以將工作區匯出為.png影像檔案，或將資料從特定視窗匯出至Excel(.xls或.xlsx)檔案。
title: 匯出工作區
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# 匯出工作區{#export-a-workspace}

{{eol}}

您可以將工作區匯出為.png影像檔案，或將資料從特定視窗匯出至Excel(.xls或.xlsx)檔案。

## 將工作區匯出為PNG檔案 {#section-f9fbe0f0a1c341e2b063cce106cac35e}

可以以「可移植網路圖形」格式保存工作區的快照(`.png` 檔案)。 將工作區儲存為 `.png` 檔案：

* **黑色背景** 複製工作區。
* **白色背景** 複製工作區的元素，並以顏色顯示在白色背景中。
* **白色背景(B&amp;W)** 以灰階方式複製工作區的元素，並在白色背景中顯示這些元素。

**將工作區匯出為.png檔案**

在工作區的標題列功能表中，按一下 **[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*.

隨即顯示「[!UICONTROL Save Image As]」對話框。

導覽至您要儲存檔案的目錄，視需要變更檔案名稱，然後按一下 **[!UICONTROL Save]**.

## 將工作區資料匯出至Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

將工作區匯出至Excel時，Data Workbench會將特定視覺效果、維度和值圖例、文字註解的資料匯出至新的Excel活頁簿，每個工作表只需一個視覺效果。

若要將工作區和個別視窗匯出至Microsoft Excel，必須符合下列要求：

* Microsoft Excel必須安裝在與Data Workbench相同的電腦上。
* 執行Data Workbench程式的使用者帳戶必須擁有存取Microsoft Excel的權限。

>[!NOTE]
>
>* 將資料匯出為Excel檔案時，會開啟新的Excel例項。 如需此程式的詳細資訊，請參閱 [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).
>* 雖然Data Workbench支援超過256列和65,536列資料，但8.0之前的Microsoft Excel版本則否。
>


如果符合這些要求，Data Workbench會自動啟動Microsoft Excel並將資料匯出至新的Excel活頁簿。 資料不會從下列視覺效果匯出：圖表、路徑瀏覽器、程式圖、散布圖和地球圖。

## 套用自訂標題 {#section-a332e157554546cb8e88922a8d7a4fa2}

除非您已為 [!UICONTROL Export] , [!UICONTROL Export title] 列出的（例如，城市表）用作工作表名稱。

1. 以滑鼠右鍵按一下視窗的上方邊框，然後按一下 **[!UICONTROL Custom title]** 欄位。
1. 輸入要應用於窗口的標題。

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>若您在 [!UICONTROL Custom title] 欄位中，此視覺效果不會與工作區一起匯出。

將工作區匯出為Excel時，包含此視窗資料的工作表會使用您指定的標題(而非 [!UICONTROL Export title] 欄位。

## 將工作區或側欄匯出至Excel {#section-360438b66d5f4734826ab463b4a01a75}

**將工作區資料匯出至新 [!DNL .xls] 或 [!DNL .xlsx] 檔案**

1. 在工作區的標題列中，按一下 **[!UICONTROL Export]** > **[!UICONTROL Export]**.
1. 指定要匯出工作區、側欄還是兩者。

## 匯出至範本Excel檔案 {#section-814772929ca64cf6b92b89d3fdd02302}

您可以將工作區中的資料匯出至範本Excel檔案(`.xls` 或 `.xlsx`)。 使用範本檔案可縮短每次匯出工作區時，您花在格式化資料上的時間。

>[!NOTE]
>
>此範本檔案必須是 `.xls` 或 `.xlsx` 檔案，而非 `.xlt` 檔案。

導出資料時，模板中的現有頁簽工作表（每個頁簽工作表都表示一個視覺效果）將重新填入工作區中的最新資料，而模板中沒有作為頁簽工作表顯示的任何新窗口將被忽略。 模板檔案中的任何其他頁簽頁都保持不變。

此外，如果您在範本Excel檔案中定義了要在產生報表時自動執行的巨集，請將巨集命名為「VSExport」。

假設您想要使用從圓形圖的表格視覺效果匯出的促銷活動資料（位於Excel檔案的其他標籤工作表上），並且想每週更新此資訊。 您可以使用模板，這樣在每次要更新資料時，就不必從表的頁簽工作表重新建立參照，即可從餅圖的頁簽工作表重新建立參照。 表格資料會在匯出時更新，而會自動更新圓形圖。

**將工作區資料導出到模板 [!DNL .xls] 或 [!DNL .xlsx] 檔案**

1. 以滑鼠右鍵按一下工作區的標題列，然後按一下 **[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**.
1. 指定要匯出工作區、側欄還是兩者。

   此 [!UICONTROL Select a template worksheet] 對話框。

1. 視需要完成下列其中一個步驟：

   * 如果您使用 `.xls` 範本檔案：

      1. 瀏覽並選取範本 `.xls` 檔案。
      1. 按一下 **[!UICONTROL Open]**。
   * 如果您使用 `.xlsx` 範本檔案：

      1. 瀏覽至範本檔案的位置。 此 `.xlsx` 檔案名未顯示。
      1. 在 [!UICONTROL File name] 欄位，類型 `.xlsx` 按一下 **[!UICONTROL Open]**. 全部 `.xlsx` 檔案名顯示在檔案清單中。

      1. 選取範本 `.xlsx` 檔案。
      1. 按一下 **[!UICONTROL Open]**。
