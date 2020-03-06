---
description: 從Premium功能表開啟Best Fit Attribution，然後依照下列步驟建立Best Fit Attribution模型。
title: 建立最符合歸因模型
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 建立最符合歸因模型{#build-a-best-fit-attribution-model}

從Premium功能表開啟Best Fit Attribution，然後依照下列步驟建立Best Fit Attribution模型。

請參閱最適 [歸因概觀](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1)。

1. 開啟最 **適歸因**。

   開啟工作區，然後按一 **[!UICONTROL Premium]** 下> **[!UICONTROL Best Fit Attribution]**。

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >Best Fit Attribution是Adobe Analytics Premium功能，需要您在設定檔中啟用Premium。 它要求您更新憑證，並將Premium描述檔新增至profile.cfg檔案。 請參閱 [DWB伺服器升級：DWB 6.3需](https://docs.adobe.com/content/help/en/data-workbench/using/install/upgrade-dwb/c-6-2-to-6-3-upgrade.html) 6.2至6.3。

1. 設定量 **[!UICONTROL Success]** 度。

   >[!NOTE]
   >
   >您可以將量度從表格拖曳至「歸 **[!UICONTROL Finder]** 因」視覺化的左窗格，或從「輸入」功能表 **中選取** 。

   按一下 **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. 度量功能表將會開啟。 ![](assets/attrib_set_success_metric.png)

   選取可識別成功轉換的量度。

1. （選用）設定「收 **入** 」量度。

   設定量度，以評估整個轉換程式的收入。

1. 設定「 **觸控** 」量度。

   >[!NOTE]
   >
   >只有在您嘗試將維度元素拖曳至視覺化中，以自動建立「成功」度量時，才需要設定「觸控度量」。

   按一下功 **[!UICONTROL Inputs]** 能表並選取「 **設定觸控**」，或從Finder拖曳量度。 ![](assets/attrib_set_touch.png)

   當維度元素用作輸入時，這將用於衍生渠道量度。

1. 設定「成 **功** 」視窗。

   按一下 [!DNL Inputs > Success Window]. 從表格中選取日期範圍，然後命名「成功」視窗。 按一 **[!UICONTROL Workspace Selection]** 下，所選日期就會被指派為「成功」度量的時間範圍。

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >由於「成功」窗口是工作站選擇，因此您可以將任何維納入「成功」窗口。

1. 設定 **[!UICONTROL Touch Window]**。

   按一下 [!DNL Inputs > Touch Window]. 從表格中選取日期範圍，然後為「觸控」視窗命名。 按一 **[!UICONTROL Workspace Selection]** 下，所選日期就會被指派為「成功」度量的時間範圍。

   ![](assets/attrib_set_touch_window.png)

   依預設， **「觸控** 」視窗會設為與視窗相同的時 **[!UICONTROL Success]** 段。

1. （選用）設定訓練篩選。

   您也可以在工作區中 **指定「訓練篩選** 」，以篩選訪客資料。

   >[!NOTE]
   >
   >在設定「成功」和「觸控」視窗時，您可以將「訓練」篩選套用至目前的工作區選擇，以進一步限制您的資料。

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >訓練集一律取自滿足「成功」視窗的訪客。 使用篩選編輯器進行篩選，即可建立「成功」視窗中報告的訪客子集。

1. 指定代表接觸的渠道量度。

   將量度拖曳至視覺化，或從「 >」功能表 [!DNL Inputs] 中選 [!DNL Add Channel] 擇。 如果您尚未為促銷活動或渠道定義量度，但確實有代表渠道的維度，視覺化可以使用觸控量度的規格自動為您建立量度。

   例如，若「觸控」量度設 [!DNL Hits]為，且給定一個名為的元素，其中包含 [!DNL dimension] 、 [!DNL Media Type] 、 [!DNL Email]和 [!DNL Press Release][!DNL Print Ad][!DNL Social Media][!DNL Hits where Media Type = Email] ，當您將元素拖放至視覺化時，視覺化將產生表單的渠道量度。

1. 按 **開始**。

   「最適分析」程式將會執行，而圖表會根據選取的輸入，顯示每個頻道的屬性。

   >[!NOTE]
   >
   >在完成的分 **析上按一下「模型完成** 」，以檢視歸因模型的統計資料。

   ![](assets/attrib_visualization.png)

完成時，圖表會顯示依頻道計算的歸因模型，以及收入度量的 *分佈* （若已設定）。 模型可在內部保存或導出到其他系統。

>[!NOTE]
>
>**[!UICONTROL Streaming]**，而 **[!UICONTROL Online]** 模式 **[!UICONTROL Offline]** 則會根據所評估資料的延遲來建立歸因模型時產生不同的效果。 在「串流」模式中，將會顯 **[!UICONTROL Model Complete]** 示詳細訊息。 在「線上」和「離線」模式中，會顯 **[!UICONTROL Local Model Complete]** 示詳細資訊。

## 選項菜單 {#section-22288867f6c8483a8a38410f4b948346}

「選 **項** 」功能表提供進階功能，以設定和顯示「最適歸因」分析。

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項菜單 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 設定訓練篩選 </span> </td> 
   <td colname="col2"> 「訓練篩選」會與「成功視窗」搭配使用，以在建立歸因模型時篩選人口。 這將提供資料子集，僅包含您要分析的訪客。 <p>注意：經驗豐富的使用者也可以運用篩選的彈性，將焦點放在成功與觸控視窗的時間線以外。 例如，除了選擇時間範圍外，您還可以選取一組反向連結網域 <i></i> ，以僅檢查這些網域的使用者屬性。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 顯示複雜篩選器說明 </span> </td> 
   <td colname="col2"> 顯示「訓練篩選」、「成功視窗」和「觸控視窗」的篩選程式碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 保存模型 </span> </td> 
   <td colname="col2"> 儲存目前的歸因模型以供日後使用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 載荷模型 </span> </td> 
   <td colname="col2"> 開啟先前儲存的歸因模型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 簡報檢視 </span> </td> 
   <td colname="col2"> 隱藏頂端功能表列以進行簡報。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>「選項&gt;進階</b> 」包含設定訓練集大小的功能，並指定在課程不平衡時要採取的方式。 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 進階&gt;訓練集大小 </span> </td> 
   <td colname="col2"> <p>設定訓練集大小。 </p> <p>注意： 250,000名訪客的預設訓練大小為「大」。 </p> 
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD"> 
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">Tiny = 50,000 </li> 
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">小= 75,000 </li> 
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">正常= 100,000 </li> 
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">大= 25萬 </li> 
     <li id="li_34B60233C84F48F1BCB8040C5195411A">巨型= 50萬 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>高級&gt;分類餘額 </b> </td> 
   <td colname="col2"> <p>根據資料集大小，識別並定義要針對類別失衡問題產生的輸入記錄數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

| 重設和移除選項 | 說明 |
|---|---|
| **[!UICONTROL Reset Model]** | 從功能表 **[!UICONTROL Reset]** 中，選取以 **[!UICONTROL Reset Model]** 清除視覺化，但保留輸入量度。 |
| **[!UICONTROL Reset All]** | 從功能 **[!UICONTROL Reset]** 表中，選 **[!UICONTROL Reset All]** 取以清除視覺化和輸入量度。 |
| **[!UICONTROL Remove]** | 在任何輸入上按一下滑鼠右鍵，並選 **[!UICONTROL Remove]** 取從選取的輸入清除量度。 |
| **[!UICONTROL Remove All]** | 以滑鼠右鍵按一 *下* ，然後選 **[!UICONTROL Remove All]** 取以清除所有輸入量度。 |

