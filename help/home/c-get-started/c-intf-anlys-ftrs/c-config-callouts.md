---
description: 圖說文字會以視覺效果中特定維度元素的虛擬選取來建立新的視覺效果，以吸引特定維度元素的注意。
title: 設定圖說文字
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# 設定圖說文字{#configure-a-callout}

圖說文字會以視覺效果中特定維度元素的虛擬選取來建立新的視覺效果，以吸引特定維度元素的注意。

通過配置儲存在配置檔案\*配置檔案名*\Context\Callout folder of the [!DNL Server]安裝資料夾中的callout檔案，可以添加或編輯圖說。 在工作表視覺效果中引起注意的特定量度的圖說稱為量度圖說。 度量標注檔案儲存在配置檔案\*配置檔案名稱*\Context\Metric Callout folder中。

如需將圖說文字或量度圖說文字新增至視覺效果的指示，請參閱[將圖說文字新增至工作區](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0)。

**要建立新類型的註解**

1. 在任何工作區中，建立包含您要以新圖說類型顯示之資料的視覺效果。 例如，如果您希望圖說文字成為表格，可建立表格視覺效果，顯示所需的量度和維度。
1. 按一下右鍵標注窗口的上邊框，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Save]窗口中，按一下![](assets/btn_folder_up.png)，按兩下&#x200B;**[!UICONTROL Context]**，然後按兩下&#x200B;**[!UICONTROL Callout]**。 在[!DNL File Name]欄位中，鍵入檔案的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。 標注檔案將保存到用戶\*工作配置檔案名*\Context\Callout folder。

   >[!NOTE]
   >
   >為圖說命名時，請選擇反映視覺效果類型及其顯示的量度和維度的描述性名稱。 例如，如果要從顯示「日」維上「會話」度量的表視覺效果建立標注，可以將標注命名為「按日的表的會話」。

1. （選用）若要讓工作設定檔的所有使用者都能使用此變更：

   1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Context]**，然後按一下&#x200B;**[!UICONTROL Callout]**。 此資料夾包含定義現有標注類型的所有可視化檔案([!DNL .vw])。

   1. 在[!DNL User]列中按一下右鍵新標注的檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。

**將圖說文字變更為量度圖說文字**

1. 在[!DNL Profile Manager]中，按一下&#x200B;**[!UICONTROL Context]**，然後按一下&#x200B;**[!UICONTROL Callout]**。 此資料夾包含定義現有標注類型的所有可視化檔案([!DNL .vw])。

1. 按一下右鍵要更改的標注類型的檔案名旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 將檔案下載到本地電腦後，[!DNL User]列中將顯示複選標籤。

1. 按一下右鍵[!DNL User]列中檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL In Notepad]**。

1. 在callout檔案中找到[!DNL metric_y = ref:]條目，並將現有值替換為單詞Metric。 下列檔案片段中醒目提示的文字會顯示插入此字詞的位置。

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

1. 按一下 **[!UICONTROL File]** > **[!UICONTROL Save As]**. 在&#x200B;**[!UICONTROL Save As]**&#x200B;視窗中，按一下，然後按兩下&#x200B;**[!UICONTROL Metric Callout]**。 在[!DNL File Name]欄位中，鍵入檔案的名稱，然後按一下&#x200B;**[!UICONTROL Save]**。 度量標注檔案將保存到用戶\*工作配置檔案名*\Context\Metric Callout folder。

1. （可選）要使此度量標注可供工作配置檔案的所有用戶使用，請在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中檔案名旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]***。
