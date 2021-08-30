---
description: 從Premium功能表開啟「最適化歸因」 ，然後依照下列步驟建立最適化歸因模型。
title: 建立最適化歸因模型
uuid: d1fd0340-1917-41bc-9a08-e78a79d084e7
exl-id: e0a42374-2500-46a3-a72a-708ab2d228db
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '870'
ht-degree: 1%

---

# 建立最適化歸因模型{#build-a-best-fit-attribution-model}

從Premium功能表開啟「最適化歸因」 ，然後依照下列步驟建立最適化歸因模型。

請參閱[最適化歸因](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-algorithmic.md#concept-237feb6e9c4d49efaf75399297dcb9d1)的概觀。

1. 開啟&#x200B;**最適化歸因**。

   開啟工作區，然後按一下「**[!UICONTROL Premium]** > **[!UICONTROL Best Fit Attribution]**」。

   ![](assets/attrib_windows_launch.png)

   >[!NOTE]
   >
   >最適化歸因是Adobe Analytics Premium的一項功能，需要您在設定檔中啟用Premium。 您必須更新憑證，並將Premium設定檔新增至profile.cfg檔案。 請參閱[DWB伺服器升級：DWB 6.3為6.2至6.3](https://experienceleague.adobe.com/docs/data-workbench/using/install/upgrade-dwb/c-6-2-to-6-3-upgrade.html)。

1. 設定&#x200B;**[!UICONTROL Success]**&#x200B;量度。

   >[!NOTE]
   >
   >您可以將量度從&#x200B;**[!UICONTROL Finder]**&#x200B;表格拖曳至歸因視覺效果的左窗格，或從&#x200B;**Inputs**&#x200B;功能表中選取。

   按一下 **[!UICONTROL Inputs]** > **[!UICONTROL Set Success]**. 量度功能表隨即開啟。![](assets/attrib_set_success_metric.png)

   選取可識別成功轉換的量度。

1. （選用）設定&#x200B;**收入**&#x200B;量度。

   設定量度以評估轉換過程中的收入。

1. 設定&#x200B;**Touch**&#x200B;量度。

   >[!NOTE]
   >
   >只有當您嘗試將維度元素拖曳至視覺效果上以自動建立成功量度時，才需要設定接觸量度。

   按一下&#x200B;**[!UICONTROL Inputs]**&#x200B;功能表，然後選取&#x200B;**設定觸控**，或從搜尋器拖曳量度。![](assets/attrib_set_touch.png)

   當維度元素用作輸入時，此量度將用來衍生管道量度。

1. 設定&#x200B;**Success**&#x200B;窗口。

   按一下「[!DNL Inputs > Success Window]」。從表格中選取日期範圍，然後為「成功」視窗命名。 按一下&#x200B;**[!UICONTROL Workspace Selection]**，便會將選取的日期指派為「成功」量度的時間範圍。

   ![](assets/attrib_set_success_window.png)

   >[!NOTE]
   >
   >由於「成功」視窗是工作站選項，因此您可以將任何維度納入「成功」視窗。

1. 設定&#x200B;**[!UICONTROL Touch Window]**。

   按一下「[!DNL Inputs > Touch Window]」。從表格中選取日期範圍，然後為觸控視窗命名。 按一下&#x200B;**[!UICONTROL Workspace Selection]**，便會將選取的日期指派為「成功」量度的時間範圍。

   ![](assets/attrib_set_touch_window.png)

   預設情況下， **Touch**&#x200B;窗口將設定為與&#x200B;**[!UICONTROL Success]**&#x200B;窗口相同的時段。

1. （選用）設定訓練篩選。

   您也可以在工作區中指定&#x200B;**訓練篩選器**&#x200B;以篩選訪客資料。

   >[!NOTE]
   >
   >在設定「成功」和「接觸」視窗中，您可以將「培訓」篩選器套用至目前的工作區選取範圍，以進一步限制您的資料。

   ![](assets/attrib_filter.png)

   >[!NOTE]
   >
   >訓練集一律從滿足「成功」視窗的訪客中提取。 使用篩選編輯器進行篩選，可以建立在成功視窗中報告的訪客子集。

1. 指定代表接觸的管道量度。

   將量度拖曳至視覺效果，或從「[!DNL Inputs] > [!DNL Add Channel]」功能表中選取。 如果您尚未為促銷活動或管道定義量度，但有代表管道的維度，則視覺效果可借由觸控量度的規格自動為您建立。

   例如，將「觸控」量度設為[!DNL Hits]，並指定[!DNL dimension]（稱為[!DNL Media Type]）並包含[!DNL Email]、[!DNL Press Release]、[!DNL Print Ad]和[!DNL Social Media]等元素的，當您將元素拖放至視覺效果時，視覺效果將產生[!DNL Hits where Media Type = Email]格式的「管道」量度。

1. 按&#x200B;**Go**&#x200B;鍵。

   將運行「最佳配適分析」過程，並且圖表將根據所選輸入顯示每個通道的屬性。

   >[!NOTE]
   >
   >在完成的分析上按一下右鍵&#x200B;**模型完成** ，查看歸因模型的統計資訊。

   ![](assets/attrib_visualization.png)

完成後，圖表會顯示每個管道計算的歸因模型，以及&#x200B;*收入*&#x200B;量度的分佈（若已設定）。 模型可以在內部保存或導出到其他系統。

>[!NOTE]
>
>**[!UICONTROL Streaming]**、和 **[!UICONTROL Online]** 模 **[!UICONTROL Offline]** 式會在根據評估資料的延遲建立歸因模型時，產生不同的效果。在「串流」模式中，將顯示詳細&#x200B;**[!UICONTROL Model Complete]**&#x200B;訊息。 在「線上」和「離線」模式中，將顯示詳細資訊&#x200B;**[!UICONTROL Local Model Complete]**。

## 選項功能表 {#section-22288867f6c8483a8a38410f4b948346}

**Options**&#x200B;功能表提供進階功能，可設定及顯示最適化歸因分析。

<table id="table_8F6F517B7DBF4259814BEC6D07A72EAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 選項功能表 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 設定培訓篩選器  </span> </td> 
   <td colname="col2"> 「訓練篩選」會與「成功視窗」搭配使用，以在建立歸因模型時篩選母體。 這將提供一個資料子集，僅包含您要分析的訪客。 <p>注意：經驗豐富的使用者也可以運用篩選器的彈性，將焦點放在成功和觸控式視窗的時間線以外。 例如，除了選取時間範圍外，您還可以選取一組<i>反向連結網域</i>，以僅檢查這些網域使用者的歸因。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 顯示複雜篩選器說明  </span> </td> 
   <td colname="col2"> 顯示「培訓篩選」、「成功視窗」和「觸控視窗」的篩選代碼。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 保存模型  </span> </td> 
   <td colname="col2"> 儲存目前的歸因模型以供日後使用。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 載荷模型  </span> </td> 
   <td colname="col2"> 開啟先前儲存的歸因模型。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 演示視圖  </span> </td> 
   <td colname="col2"> 隱藏頂部菜單欄以進行演示。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>「選項」</b> &gt;「高級」包括設定訓練集大小的功能，以及指定在類別不均衡時採取的方法。 </p> </td> 
   <td colname="col2"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="uicontrol"> 高級&gt;培訓集大小  </span> </td> 
   <td colname="col2"> <p>設定培訓集大小。 </p> <p>注意： 250,000位訪客的預設訓練大小為「大」。 </p> 
    <ul id="ul_5F17C60227C34A85A2C476A32F2B5DCD"> 
     <li id="li_A076FC2AD0214ADDBFCFD82AEA5F0880">小= 50,000 </li> 
     <li id="li_17E77E01D5374068BEBC80B3AD4CCD41">小= 75,000 </li> 
     <li id="li_7F6B4834742A4BFCBC3DB214425B88C3">一般= 100,000 </li> 
     <li id="li_0BB7F791603745028CFC661EBC94D8B4">大= 250,000 </li> 
     <li id="li_34B60233C84F48F1BCB8040C5195411A">大= 50萬 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>高級&gt;分類餘額  </b> </td> 
   <td colname="col2"> <p>根據資料集大小識別並定義要針對類別不平衡問題產生的輸入記錄數。 </p> </td> 
  </tr> 
 </tbody> 
</table>

| 重設和移除選項 | 說明 |
|---|---|
| **[!UICONTROL Reset Model]** | 從&#x200B;**[!UICONTROL Reset]**&#x200B;功能表中，選取&#x200B;**[!UICONTROL Reset Model]**&#x200B;以清除視覺效果，但保留輸入量度。 |
| **[!UICONTROL Reset All]** | 從&#x200B;**[!UICONTROL Reset]**&#x200B;功能表中，選取&#x200B;**[!UICONTROL Reset All]**&#x200B;以清除視覺效果和輸入量度。 |
| **[!UICONTROL Remove]** | 按一下右鍵任何輸入，然後選擇&#x200B;**[!UICONTROL Remove]**&#x200B;以從選定輸入中清除度量。 |
| **[!UICONTROL Remove All]** | 按一下右鍵&#x200B;*頻道*&#x200B;並選擇&#x200B;**[!UICONTROL Remove All]**&#x200B;以清除所有輸入度量。 |
