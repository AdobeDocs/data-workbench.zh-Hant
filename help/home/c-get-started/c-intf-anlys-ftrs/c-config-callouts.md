---
description: 註解會以視覺化中特定維度元素的虛擬選取來建立新的視覺化，以吸引特定維度元素的注意。
solution: Analytics
title: 配置註解
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置註解{#configure-a-callout}

註解會以視覺化中特定維度元素的虛擬選取來建立新的視覺化，以吸引特定維度元素的注意。

通過配置儲存在配置檔案\*配置檔案名*\Context\Callout folder of the 安裝資料夾中的註解檔案，可以添加或編輯註解 [!DNL Server] 。 在工作表視覺化中引起特定量度注意的量度稱為量度量度。 量度圖說檔案會儲存在描述檔\*描述檔名稱*\Context\Metric Callout folder中。

如需將圖說或量度圖說新增至視覺化的指示，請參 [閱新增圖說至工作區](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0)。

**建立新類型的註解**

1. 在任何工作區中，建立包含您要顯示在新註解類型中之資料的視覺化。 例如，如果您希望圖說成為表格，您會建立表格視覺化，顯示所要的量度和維度。
1. 按一下右鍵註解窗口的上邊框，然後按一下 **[!UICONTROL Save]**。
1. 在視窗 [!DNL Save] 中，按一 ![](assets/btn_folder_up.png)下、連按兩 **[!UICONTROL Context]**&#x200B;下，然後按兩下 **[!UICONTROL Callout]**。 在欄位 [!DNL File Name] 中，輸入檔案的名稱，然後按一下 **[!UICONTROL Save]**。 將callout檔案保存到「用戶」(User)\*工作配置檔案名稱*\Context\Callout folder。

   >[!NOTE]
   >
   >在命名圖說時，選擇反映視覺化類型及其顯示的量度和維度的描述性名稱。 例如，如果要從顯示「日」維上「會話」度量的表可視化建立圖說，可以將圖說命名為「按日表列出的會話」。

1. （可選）要將此更改提供給工作配置檔案的所有用戶，請執行以下操作：

   1. 在中，單 [!DNL Profile Manager]擊，然 **[!UICONTROL Context]**&#x200B;後按一下 **[!UICONTROL Callout]**。 此資料夾包含定義現有註解類型 [!DNL .vw]的所有可視化檔案()。

   1. 按一下右鍵列中新註解檔案名旁的複選標籤，然 [!DNL User] 後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。

**將圖說更改為度量圖說**

1. 在中，單 [!DNL Profile Manager]擊，然 **[!UICONTROL Context]**&#x200B;後按一下 **[!UICONTROL Callout]**。 此資料夾包含定義現有註解類型 [!DNL .vw]的所有可視化檔案()。

1. 按一下右鍵要更改的註解類型檔案名旁邊的複選標籤，然後按一下 **[!UICONTROL Make Local]**。 將檔案下載到本地電腦後，該列中會顯示複選 [!DNL User] 標籤。

1. 在欄中，以滑鼠右鍵按一下檔案名稱旁的核取標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**。

1. 在callout文 [!DNL metric_y = ref:] 件中找到該條目，並用單字「度量」替換現有值。 下列檔案片段中反白顯示的文字會顯示您插入此字詞的位置。

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. 按一下 **[!UICONTROL File]** > **[!UICONTROL Save As]**. 在視窗 **[!UICONTROL Save As]** 中，按一下，然後按兩下 **[!UICONTROL Metric Callout]**。 在欄位 [!DNL File Name] 中，輸入檔案的名稱，然後按一下 **[!UICONTROL Save]**。 度量圖說檔案會儲存至「使用者」(User)\*工作描述檔名稱*\Context\Metric Callout folder。

1. （可選）要使此度量註解對工作配置檔案的所有用戶可用，請在列中按一下右鍵檔案名旁的複選標籤，然後按一下 [!DNL Profile Manager]> [!DNL User] &lt; **[!UICONTROL Save to]** > ***[!UICONTROL working profile name]***。

