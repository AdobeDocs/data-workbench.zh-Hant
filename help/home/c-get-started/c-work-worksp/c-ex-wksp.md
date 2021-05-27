---
description: 您可以將工作區匯出為.png影像檔案，或將資料從特定視窗匯出至Excel(.xls或.xlsx)檔案。
title: 匯出工作區
uuid: 59ea6e46-d2e9-41f9-9c8f-e3071eb65424
exl-id: 87416ddf-2ac0-4f95-ae8e-71051061c757
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '774'
ht-degree: 1%

---

# 匯出工作區{#export-a-workspace}

您可以將工作區匯出為.png影像檔案，或將資料從特定視窗匯出至Excel(.xls或.xlsx)檔案。

## 將工作區導出為PNG檔案{#section-f9fbe0f0a1c341e2b063cce106cac35e}

可以以「可移植網路圖形」格式（`.png`檔案）保存工作區的快照。 將工作區儲存為`.png`檔案時，可使用下列顏色選項：

* **黑色** 背景會複製顯示的工作區。
* **白** 色背景會以顏色複製工作區的元素，並在白色背景中顯示這些元素。
* **白色背景(B&amp;W)** 會以灰階方式複製工作區的元素，並在白色背景中顯示這些元素。

**將工作區匯出為.png檔案**

在工作區的標題欄功能表中，按一下「**[!UICONTROL Export]** > **[!UICONTROL Export PNG]** > *&lt;**[!UICONTROL color option]**>*」。

將出現[!UICONTROL Save Image As]對話框。

導航至要保存檔案的目錄，根據需要更改檔案的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。

## 將工作區資料匯出至Microsoft Excel {#section-fe214e3dbc364d2eba3834d62d295acb}

將工作區匯出至Excel時，Data Workbench會將特定視覺效果、維度和值圖例、文字註解的資料匯出至新的Excel活頁簿，每個工作表只需一個視覺效果。

若要將工作區和個別視窗匯出至Microsoft Excel，必須符合下列要求：

* Microsoft Excel必須安裝在與Data Workbench相同的電腦上。
* 運行Data Workbench進程的用戶帳戶必須具有訪問Microsoft Excel的權限。

>[!NOTE]
>
>* 將資料匯出為Excel檔案時，會開啟新的Excel例項。 有關此過程的詳細資訊，請參閱[http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。
>* 雖然Data Workbench支援超過256列和65,536列資料，但8.0之前的Microsoft Excel版本則否。
>



如果滿足這些要求，Data Workbench會自動啟動Microsoft Excel並將資料匯出至新的Excel活頁簿。 資料不會從下列視覺效果匯出：圖表、路徑瀏覽器、程式圖、散布圖和地球圖。

## 應用自定義標題{#section-a332e157554546cb8e88922a8d7a4fa2}

除非您已在[!UICONTROL Export]菜單上為窗口指定了「自定義標題」，否則將使用列出的[!UICONTROL Export title]（例如，城市表）作為工作表名稱。

1. 按一下右鍵窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Custom title]**&#x200B;欄位。
1. 輸入要應用於窗口的標題。

   ![](assets/mnu_window_TitleBar_Export.png)

>[!NOTE]
>
>如果您在[!UICONTROL Custom title]欄位中輸入連字型大小(-)，此視覺效果不會與工作區一併匯出。

將工作區導出為Excel時，包含此窗口資料的工作表將使用您指定的標題命名，而不是[!UICONTROL Export title]欄位中的標題。

## 將工作區或側欄匯出至Excel {#section-360438b66d5f4734826ab463b4a01a75}

**將工作區資料匯出至新或 [!DNL .xls] 檔 [!DNL .xlsx] 案**

1. 在工作區的標題列中，按一下「**[!UICONTROL Export]** > **[!UICONTROL Export]**」。
1. 指定要匯出工作區、側欄還是兩者。

## 匯出至範本Excel檔案{#section-814772929ca64cf6b92b89d3fdd02302}

您可以將工作區中的資料匯出至範本Excel檔案（`.xls`或`.xlsx`）。 使用範本檔案可縮短每次匯出工作區時，您花在格式化資料上的時間。

>[!NOTE]
>
>此模板檔案必須是`.xls`或`.xlsx`檔案，而不是`.xlt`檔案。

導出資料時，模板中的現有頁簽工作表（每個頁簽工作表都表示一個視覺效果）將重新填入工作區中的最新資料，而模板中沒有作為頁簽工作表顯示的任何新窗口將被忽略。 模板檔案中的任何其他頁簽頁都保持不變。

此外，如果您在範本Excel檔案中定義了要在產生報表時自動執行的巨集，請將巨集命名為「VSExport」。

假設您想要使用從圓形圖的表格視覺效果匯出的促銷活動資料（位於Excel檔案的其他標籤工作表上），並且想每週更新此資訊。 您可以使用模板，這樣在每次要更新資料時，就不必從表的頁簽工作表重新建立參照，即可從餅圖的頁簽工作表重新建立參照。 表格資料會在匯出時更新，而會自動更新圓形圖。

**將工作區資料導出到模板或 [!DNL .xls] 檔 [!DNL .xlsx] 案**

1. 以滑鼠右鍵按一下工作區的標題列，然後按一下&#x200B;**[!UICONTROL Export]** > **[!UICONTROL Export to Excel from Template]**。
1. 指定要匯出工作區、側欄還是兩者。

   [!UICONTROL Select a template worksheet]對話框開啟。

1. 視需要完成下列其中一個步驟：

   * 如果您使用`.xls`範本檔案：

      1. 瀏覽並選擇模板`.xls`檔案。
      1. 按一下 **[!UICONTROL Open]**。
   * 如果您使用`.xlsx`範本檔案：

      1. 瀏覽至範本檔案的位置。 未顯示`.xlsx`檔案名。
      1. 在[!UICONTROL File name]欄位中，鍵入`.xlsx`並按一下&#x200B;**[!UICONTROL Open]**。 所有`.xlsx`檔案名都顯示在檔案清單中。

      1. 選擇模板`.xlsx`檔案。
      1. 按一下 **[!UICONTROL Open]**。
