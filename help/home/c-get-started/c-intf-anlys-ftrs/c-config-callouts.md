---
description: 註解會以視覺化中特定維度元素的虛擬選取來建立新的視覺化，以吸引特定維度元素的注意。
title: 設定圖說文字
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# 設定圖說文字{#configure-a-callout}

註解會以視覺化中特定維度元素的虛擬選取來建立新的視覺化，以吸引特定維度元素的注意。

通過配置儲存在Profiles\*profile name*\Context\Callout folder of the [!DNL Server]安裝資料夾中的callout檔案，可以添加或編輯註解。 在工作表視覺化中引起特定量度注意的量度稱為量度量度。 量度圖說檔案會儲存在描述檔\*描述檔名稱*\Context\Metric Callout folder中。

如需將圖說或度量圖說新增至視覺化的指示，請參閱[將圖說新增至工作區](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0)。

**建立新類型的註解**

1. 在任何工作區中，建立包含您要顯示在新註解類型中之資料的視覺化。 例如，如果您希望圖說成為表格，您會建立表格視覺化，顯示所要的量度和維度。
1. 按一下右鍵註解窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Save]視窗中，按一下![](assets/btn_folder_up.png)，按兩下&#x200B;**[!UICONTROL Context]**，然後按兩下&#x200B;**[!UICONTROL Callout]**。 在[!DNL File Name]欄位中，輸入檔案的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。 將callout檔案保存到「用戶」(User)\*工作配置檔案名稱*\Context\Callout folder。

   >[!NOTE]
   >
   >在命名圖說時，選擇反映視覺化類型及其顯示的量度和維度的描述性名稱。 例如，如果要從顯示「日」維上「會話」度量的表可視化建立圖說，可以將圖說命名為「按日表列出的會話」。

1. （可選）要將此更改提供給工作配置檔案的所有用戶，請執行以下操作：

   1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Context]** ，然後按一下&#x200B;**[!UICONTROL Callout]**。 此資料夾包含定義現有註解類型的所有可視化檔案([!DNL .vw])。

   1. 按一下右鍵[!DNL User]列中新註解檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]**>*。

**將圖說更改為度量圖說**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Context]** ，然後按一下&#x200B;**[!UICONTROL Callout]**。 此資料夾包含定義現有註解類型的所有可視化檔案([!DNL .vw])。

1. 按一下右鍵要更改的註解類型檔案名旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 將檔案下載到本地電腦後，[!DNL User]列中將顯示複選標籤。

1. 按一下右鍵[!DNL User]列中檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL In Notepad]**。

1. 在callout檔案中找到[!DNL metric_y = ref:]條目，並用單字「度量」替換現有值。 下列檔案片段中反白顯示的文字會顯示您插入此字詞的位置。

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

1. 按一下 **[!UICONTROL File]** > **[!UICONTROL Save As]**. 在&#x200B;**[!UICONTROL Save As]**&#x200B;視窗中，按一下一次，然後按兩下&#x200B;**[!UICONTROL Metric Callout]**。 在[!DNL File Name]欄位中，輸入檔案的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。 度量圖說檔案會儲存至「使用者」(User)\*工作描述檔名稱*\Context\Metric Callout folder。

1. （可選）要使此度量註解可用於工作配置檔案的所有用戶，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL working profile name]***。
