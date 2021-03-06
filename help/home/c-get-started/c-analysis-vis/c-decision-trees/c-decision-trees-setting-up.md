---
description: 透過識別正面案例並新增度量和維度輸入來建立決策樹，以評估資料並探索決策樹。
title: 建立決策樹
uuid: 5790d322-5460-444d-95d8-a06696f9a55f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 建立決策樹{#building-a-decision-tree}

透過識別正面案例並新增度量和維度輸入來建立決策樹，以評估資料並探索決策樹。

請依照下列步驟建立決策樹。

1. 開啟新工作區。

   開啟新工作區後，您可能需要按一下「新增 **>暫** 時解除鎖定 ****」。

1. 若要開啟「決策樹產生器」，請以滑鼠右鍵按一 **[!UICONTROL Visualization]** 下> **Predictive Analytics** >分類 **>** Decision Tree Builder ****。

1. 設定 **正面大小寫**。

   通過在「查找器」(Finder)或表格中的維元素中選擇維，或在「設計篩選器」(Design Filter)中設計篩選器，可以為決策樹定義正面大小寫。 事實上，正面案例可以是工作區中多個選擇的組合，包括篩選器、維度、元素和所有類型的資料工作台視覺化值。

   * **設計並套用篩選器** ，做為正面案例。 在工作區中按一下滑鼠右鍵，然後選取 **[!UICONTROL Tools]** > **[!UICONTROL Filter Editor]** 以設計並套用篩選。

   * 新增 **維度** ，做為正面案例。 在工作區中，按一下滑鼠右鍵並選 **取「工具** >尋找器 **」(或** 在左窗格中 **[!UICONTROL Add]****[!UICONTROL Finders]** 選取>)。 在「搜尋」欄位中輸入維 **度名稱** ，然後選取維度。

   * 新增 **量度** ，做為正面案例。 以滑鼠右鍵按一下並選 **取「工具** >尋找器 **」，或在左窗格** 中選 **[!UICONTROL Add]****[!UICONTROL Finders]** 取「量度」表格。 選取量度作為正面案例。

   * 將「 **維度元素** 」新增為正面案例。 在工作區中按一下滑鼠右鍵，然 **[!UICONTROL Table]** 後選取以開啟維度元素，然後從維度元素中選取以設定正面大小寫。

1. 按一下 **[!UICONTROL Options]** > **[!UICONTROL Set Positive Case]**.

   這會設定正面大小寫，並讓您命名。 名稱將顯示在工作區 **[!UICONTROL Positive Case]** 的標題下。

   >[!NOTE]
   >
   >當您設定正面案例時，「決策樹」會使用目前的工作區選擇，可定義為符合工作區中目前選擇的「訪客」（或任何已定義的頂層可計數，但在大多數情況下為「訪客」）。 這些組合為單一正面案例（而非多個正面案例）的單一篩選。

   當沒 **[!UICONTROL Set Positive Case]** 有選取範圍時，按一下會清除正面大小寫。

1. （選用）選 **[!UICONTROL Set Population Filters]** 取以定義要分類的訪客人數。

   如果未套用人口篩選，則會從所有訪客中擷取訓練集（預設為「每個人」）。

   >[!NOTE]
   >
   >按一下 **[!UICONTROL Show Complex Filter Description]** 以檢視「正面大小寫」和「填入篩選」的篩選指令碼。

1. 新增 **量度**、維 **度**&#x200B;和 **維度元素** 。

   您可以從Finder面板或個別維度元素的表格中拖放來選取輸入。 您也可以從工具列的 **[!UICONTROL Metrics]** 選單中選取。

   * 新增 **量度** 作為輸入。

      從工具列中選取「量度」。 按 **Ctrl** + **Alt** ，將一或多個量度拖曳至「決策樹產生器」。

      量度會以獨特的色 **彩編碼顯示在** 「輸入（量度）」清單中。

      ![](assets/decision_tree_add_Metrics_inputs.png)

   * 新增 **維度** 作為輸入。

      在工作區中，以滑鼠右鍵按一下並選 **取「工具** > **Finder** 」，然後在「搜尋」欄位中輸入 **** 維度名稱。 按 **Ctrl** + **Alt**，選取維度，然後將維度拖曳至「決策樹產生器」。

      維度會以獨特的色 **彩編碼出現在「輸入（維度）** 」清單中。

   * 新增 **維度元素** ，做為輸入。

      在工作區中，按一下右鍵並選擇「維」(Dimension)表。 選擇「維元素」，按 **Ctrl** + **Alt**，然後將選定的元素拖動到「決策樹生成器」。

      尺寸元素將以獨特的色 **彩編碼顯示在「輸入（元素）** 」清單中。
   >[!IMPORTANT]
   >
   >您最多可以選取14個要評估的輸入。 如果新增了太多輸入，將會出現錯誤訊息。

1. 從工 **[!UICONTROL Go]** 具列中選取。

   決策樹會根據選取的維度和量度建立。 購物車新增等簡單量度的建立速度會很快，而包含多個資料點的瀏覽持續時間等複雜維度的建立速度會更慢，轉換時會顯示完成百分比。 然後，樹狀圖將會修剪並開啟，以供使用者互動。 維度和量度輸入會以色碼與節點名稱一致。

   ![](assets/decision_tree_builder.png)

   如果樹已修剪，且在修剪的分支後有 **True** 或 **False** 預測，葉節點會顯示為綠色(true)或紅色(false)。

   >[!NOTE]
   >
   >從資料集提取訓練範例，供樹狀建立器使用。 資料工作台使用80%的樣本來建立樹狀結構，其餘20%的樣本則用來評估樹狀結構模型的準確性。

1. 使用驗證準確 **[!UICONTROL Confusion Matrix]**&#x200B;性。

   按一 **[!UICONTROL Options]** 下> **[!UICONTROL Confusion Matrix]** 以檢視「正確性」、「召回率」、「精確度」和「F分數」值。 接近100%越好。

   「混淆矩陣」使用值組合，提供模型的4種精確度計數：

   * 實際正數(AP)
   * 預計正數(PP)
   * 實際負值(AN)
   * 預計負值(PN)
   >[!TIP]
   >
   >這些資料是通過應用對20%測試資料的最終評分模型得到的，該模型已被稱為真實答案。 如果分數大於50%，則會預測為正面案例（與定義的篩選器相符）。 然後，精度=(TP + TN)/(TP + FP + TN + FN)，召回率= TP /(TP + FN)，精度= TP /(TP + FN)。

1. **探索決策樹**。

   產生決策樹後，您可以檢視預測路徑並識別符合定義准則的所有訪客。 該樹基於每個分支的位置和顏色編碼來識別每個分支的輸入拆分。 例如，如果選擇「反向連結網域」節點，則指向該分割的節點將按樹左側的顏色代碼列出。

   您可以選擇葉節點以選擇決策樹的分支（規則集）。

   對於此示例：如果瀏覽持續時間小於1，則不存在促銷活動，至少存在一個頁面檢視，沒有電子郵件註冊，並且至少存在一次瀏覽。 對此符合標準和下單的預測 **為94.73** %。

   ![](assets/decision_tree_explore.png)

   **決策樹交互**:可以使用標準 **Ctrl** -click **to add，或** Shift-click to delete，在樹上選擇多個節點。

   **色標節點**:節點的顏色與「資料工作台」指派的輸入維度和量度的顏色相符。

   修剪的分支葉級的亮綠色和紅色節點將節點預測為True或False。

   | ![](assets/decision_tree_node_true.png) 明亮的綠色 | 識別節點等於true且符合所有條件。 |
   |---|---|
   | ![](assets/decision_tree_node_false.png) 鮮紅 | 識別節點等於false，但並非所有條件都符合。 |

1. **保存決策樹**。

   可以以不同格式保存決策樹：

   ![](assets/decison_tree_save.png)

   * 預測標籤語言(**PMML**)，一種XML檔案格式，應用程式用來描述和交換決策樹模型。
   * **顯示** 「是」或「是」的簡單列和行、百分比、成員數和輸入值的文本。
   * 具有 **與預測結果元素** 對應的分支的維。

