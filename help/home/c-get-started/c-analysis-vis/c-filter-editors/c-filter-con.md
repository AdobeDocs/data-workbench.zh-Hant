---
description: 有關使用篩選條件的資訊，包括建立新篩選和新增條件至新篩選。
solution: Analytics
title: 使用篩選條件
topic: Data workbench
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用篩選條件{#working-with-filter-conditions}

有關使用篩選條件的資訊，包括建立新篩選和新增條件至新篩選。

## Create a filter {#section-70ba51ae625e493fa3ca70b93ffba406}

* 以滑鼠右鍵按一下>，在工作區中開啟篩選器編 **[!UICONTROL Add Visualization]** 輯器 **[!UICONTROL Filter Editor]**。

   -或-

* 如果您已開啟篩選編輯器並載入篩選器，請以滑鼠右鍵按一下目前篩選器的名稱，然後按一下 **[!UICONTROL New Blank Filter]**。

## 新增條件至新篩選 {#section-50986db80f1148c489630a8a63fe9f28}

1. 建立新篩選。 請確定「設計篩選」已反白顯示（與「套用篩選」相反），表示您正在「設計篩選」模式中工作。
1. 在標示的區域內按一下滑鼠右鍵， **[!UICONTROL Right-click to build filter]** 然後選取下列其中一個選項：

   * 若要建立包含篩選，請按一下 **[!UICONTROL Include group with]**。
   * 若要建立排除篩選，請按一下 **[!UICONTROL Exclude group with]**。

1. 選取要新增至篩選的條件類型。

   下表說明可用的篩選條件類型：

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 條件類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>工作區選擇 </p> </td> 
   <td colname="col2"> <p>根據工作區中的選擇定義篩選條件。 僅當工作區中存在一個或多個選擇時，此選項才可用。 </p> <p>要查看有關選擇的詳細資訊，請按一下右鍵該條件，然後按一下「查看詳細 <span class="uicontrol"> 資訊」</span>。 該條件將出現一個註解。 </p> <p>如果在工作區中進行了另一個選擇，則可以將選擇添加為第一個選擇的子條件。 這些選項將作為邏輯AND分組在一起。 因此，條件所包含或排除的資料必須滿足所有工作區選擇。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>至少一個 </p> </td> 
   <td colname="col2">根據您選擇的維中至少存在一個（任何）元素來定義篩選條件。 要編輯條件，請按一下右鍵該條件，然後按一下「將條 <span class="uicontrol"> 件</span> 更改為」。 按一下其中一個可用維度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>公式 </p> </td> 
   <td colname="col2"> <p>根據您輸入的公式定義篩選條件。 您必須使用適當的語法，才能讓篩選器運作。 </p> <p> <p>注意：如需定義篩選器的語法的詳細資訊，請參 <a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> 閱篩選運算式的語法</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>量度值 </p> </td> 
   <td colname="col2"> <p>根據您指定的量度值定義篩選條件。 </p> <p>要定義條件，請執行以下步驟： 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">以滑鼠右鍵 <span class="uicontrol"> 按一下[選擇層級]</span> &gt; 「變更層級 <span class="uicontrol"></span> 」，從資料集的維度清單中選取層級和度量。 </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">以滑鼠右鍵 <span class="uicontrol"> 按一下[選擇量度]</span> &gt; <span class="uicontrol"> 變更量度</span> ，從資料集的量度清單中選取量度。 </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">以滑鼠右鍵按一下「小於」，然後按一下「變更比較 <span class="uicontrol"></span> 」，以選取其中一個可用的比較條件（小於、大於、精確、至少或最多）。 </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">輸入所需的量度值。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>first/last </p> </td> 
   <td colname="col2"> <p>定義可讓您包含或排除具有指定維度之層級的篩選。 例如，您可以指定要包含（或排除）的第一個／最後一個篩選： </p> <p>最後一個頁面檢視的頁面為/hme/rts/ <span class="filepath"> Our Rates的作業</span>。 </p> <p>要定義「第一個／最後一個」條件，請執行以下操作： 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">在「篩 <span class="uicontrol"> 選編輯器</span> 」中，選擇「包含群組(Include group with <span class="uicontrol"> )」或「排除群組with(Exclude group with</span> ) <span class="uicontrol"> &gt; first/last</span> （第一個／最後一個）」作為新條件。 </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">以滑鼠右鍵按 <span class="uicontrol"> 一下[選擇容器]</span> &gt; <span class="uicontrol"> 變更容器</span> ，以選取容器。 </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">以滑鼠右鍵 <span class="uicontrol"> 按一下</span> ，或 <span class="uicontrol"> 先按一下</span> ，以指定層級。 </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">按一下滑鼠右鍵以指定維度，然後在可用欄位中輸入值。 </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">按一下<span class="uicontrol">「套用」</span>。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

此範例中的篩選器會為使用者定義第一個／最後一個篩選器，其最後一個頁面檢視是 [!DNL /hme/rts/Our Rates]:

![](assets/client-fil2.png)

1. （可選）若要新增更多條件至篩選，請在您要建立篩選的視窗區域內按一下滑鼠右鍵，然後選取篩選的類型（請參閱步驟2）和條件規則（請參閱步驟3）。

   >[!NOTE]
   >
   >多個包含條件被分組為邏輯OR。 因此，過濾器所包括的資料必須滿足至少一個定義的包含條件。 多個排除條件也會分組為邏輯OR。 要排除，資料必須滿足至少一個排除條件。

此範例中的篩選器定義資料子集，其中包含影片檢視者（使用者），他們對大量影片評分，但未給予任何一部影片高分（4或5）。 此篩選器（適當命名為Very Hard to Please）包含兩個條件：

* **量度值條件：** 此條件包括對至少500部影片評級的使用者。
* **工作區選擇條件：** 此條件不包括給任何一部影片評分4或5的使用者。 註解會告訴您4和5是從「分數」維度選取的元素。

![](assets/vis_FilterEditor_ExampleMovies.png)

## 刪除篩選條件 {#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>只有在「設計篩選」模式下工作時，才可刪除條件。 如果您已將篩選套用至工作區，您必須按一下「設計篩選」以返回「設計篩選」模式，才能刪除一或多個篩選條件。

* 按一 **下條件** 左側的x以刪除它。

## 編輯條件說明 {#section-5015fd2c88ed4b6a95be7f0d53be2db0}

您可以新增說明至新增至篩選器的每個條件。 您可以視需要編輯或移除說明。

>[!NOTE]
>
>只有在「設計篩選」模式下工作時，才會顯示條件說明。

* 在條件上按一下滑鼠右鍵，然後按一下 **[!UICONTROL Edit description]**。

   * 要添加或編輯說明，請在欄位中鍵入 [!DNL Edit condition description] 說明。 說明會在篩選器編輯器視窗中，以引號顯示在條件上方。

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* 要刪除說明，請按一下 **[!UICONTROL Remove description]**。 條件仍保留在篩選器編輯器窗口中。

