---
description: 有關使用篩選條件的資訊，包括建立新篩選器和將條件新增至新篩選器。
title: 使用篩選條件
uuid: a75fcb21-be5c-452a-8632-86cd78db15cb
exl-id: 15745b0c-2754-4f8b-acfd-a6bd5886ecf8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 1%

---

# 使用篩選條件{#working-with-filter-conditions}

有關使用篩選條件的資訊，包括建立新篩選器和將條件新增至新篩選器。

## 建立篩選器 {#section-70ba51ae625e493fa3ca70b93ffba406}

* 在工作區中按一下滑鼠右鍵，按一下「**[!UICONTROL Add Visualization]** > **[!UICONTROL Filter Editor]**」 ，開啟篩選器編輯器。

   -或-

* 如果已開啟篩選器編輯器且已載入篩選器，請以滑鼠右鍵按一下目前篩選器的名稱，然後按一下&#x200B;**[!UICONTROL New Blank Filter]**。

## 將條件新增至新篩選器{#section-50986db80f1148c489630a8a63fe9f28}

1. 建立新篩選器。 請確定「設計篩選」已反白顯示（與「套用篩選」相對），表示您正在「設計篩選」模式中工作。
1. 在標籤為&#x200B;**[!UICONTROL Right-click to build filter]**&#x200B;的區域內按一下右鍵，然後選擇以下選項之一：

   * 若要建立包含篩選器，請按一下&#x200B;**[!UICONTROL Include group with]**。
   * 若要建立排除篩選，請按一下&#x200B;**[!UICONTROL Exclude group with]**。

1. 選取要新增至篩選的條件類型。

   下表提供可用篩選條件類型的說明：

<table id="table_3B35B57FF32349F09E91E8256FF1672A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 條件類型 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>工作區選取 </p> </td> 
   <td colname="col2"> <p>根據工作區中的選取項目定義篩選條件。 只有在工作區中存在一個或多個選擇時，此選項才可用。 </p> <p>要查看有關選擇的更多資訊，請按一下右鍵條件，然後按一下<span class="uicontrol">查看詳細資訊</span>。 條件的註解隨即出現。 </p> <p>如果在工作區中進行另一個選擇，則可將該選擇添加為第一個選擇的子條件。 這些選項將作為邏輯AND一起分組。 因此，條件包含或排除的資料必須滿足所有工作區選取範圍。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>至少一個 </p> </td> 
   <td colname="col2">根據您選擇的維的至少一個（任何）元素的存在定義篩選條件。 若要編輯條件，請以滑鼠右鍵按一下條件，然後按一下「<span class="uicontrol">將</span>條件變更為」。 按一下任一可用維。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>公式 </p> </td> 
   <td colname="col2"> <p>根據您輸入的公式定義篩選條件。 您必須使用適當的語法，篩選才能運作。 </p> <p> <p>注意：有關定義篩選器的語法的資訊，請參閱<a href="../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15">篩選器運算式的語法</a>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>量度值 </p> </td> 
   <td colname="col2"> <p>根據您指定的量度值定義篩選條件。 </p> <p>若要定義條件，請依照下列步驟操作： 
     <ul id="ul_B69D31258A36460E94535709239CD165"> 
      <li id="li_51317A681E654DD7A9D997DF9F2F22BA">按一下右鍵<span class="uicontrol"> [選擇級別]</span> &gt; <span class="uicontrol">更改級別</span>以從資料集中的維清單中選擇級別和度量。 </li> 
      <li id="li_975E56C335824FDCB988344952DE2E9F">按一下右鍵<span class="uicontrol"> [選擇度量]</span> &gt; <span class="uicontrol">變更度量</span>以從資料集中的度量清單中選取度量。 </li> 
      <li id="li_D00B3AF3D8DE472C9D0E9EABBBCAAF61">按一下右鍵「小於」，然後按一下「更改比較」(<span class="uicontrol"> Change comparison</span>)以選擇可用比較條件之一（小於、大於、完全、至少或最多）。 </li> 
      <li id="li_3334CE0A0950448590E5442AB243F46B">輸入量度所需的值。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>首次/上次 </p> </td> 
   <td colname="col2"> <p>定義一個篩選器，可讓您包含或排除具有指定維度的層級。 例如，您可以指定要包含（或排除）的第一個/最後一個篩選器： </p> <p>最後一個「頁面檢視」的頁面為<span class="filepath"> /hme/rts/Our Rates</span>的工作階段。 </p> <p>若要定義「第一個/最後一個」條件： 
     <ul id="ul_5AD916DA093844B8AC70127B1EB9BFC8"> 
      <li id="li_AB9FF22ADC8843A79856FED60B9478FA">選擇<span class="uicontrol">包含包含</span>的組或<span class="uicontrol">排除包含</span> &gt; <span class="uicontrol">的組，作為篩選器編輯器中的新條件。</span> </li> 
      <li id="li_92F536FCC2A74DDE97F66C6C45ACC3DC">按一下右鍵<span class="uicontrol"> [選擇容器]</span> &gt; <span class="uicontrol">更改容器</span>以選擇容器。 </li> 
      <li id="li_1E5DBE04ABC74D84B7C0EF6886CDB5DC">按一下右鍵<span class="uicontrol"> first</span>或<span class="uicontrol"> last</span>以指定級別。 </li> 
      <li id="li_8B73EBF5D06E4513B5F0376EB2805D1C">按一下滑鼠右鍵以指定維度，然後在可用欄位中輸入值。 </li> 
      <li id="li_A9E02EF6C6004DDF9B00EB853B6E54EE">按一下<span class="uicontrol">「套用」</span>。 </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

此範例中的篩選器定義了最後一個頁面檢視為[!DNL /hme/rts/Our Rates]的使用者的第一個/最後一個篩選器：

![](assets/client-fil2.png)

1. （可選）若要新增更多條件至篩選器，請在建立篩選器的視窗區域內按一下滑鼠右鍵，並選取篩選器類型（請參閱步驟2）和條件規則（請參閱步驟3）。

   >[!NOTE]
   >
   >多個包含條件會分組為邏輯OR。 因此，由過濾器包括的資料必須滿足所定義的包含條件中的至少一個。 多個排除條件也會分組為邏輯OR。 若要排除，資料必須至少滿足其中一個排除條件。

此範例中的篩選器定義了資料子集，該子集由對大量電影評分但未給予任何一部電影高分（4或5）的電影檢視者（使用者）組成。 此篩選器（適當命名為「非常難以取得」）包含兩個條件：

* **量度值條件：** 條件包含對至少500部電影進行分級的使用者。
* **工作區選取條件：** 條件會排除對任何一部影片給予4分或5分的使用者。註解會告訴您4和5是從「分數」維度中選取的元素。

![](assets/vis_FilterEditor_ExampleMovies.png)

## 刪除篩選條件{#section-3092e0d7ac624885b8fe24616279de13}

>[!NOTE]
>
>只有在「設計篩選」模式下工作時，才可刪除條件。 如果您已將篩選器套用至工作區，則必須按一下「設計篩選器」以返回「設計篩選器」模式，才能刪除一或多個篩選器的條件。

* 按一下條件左側的&#x200B;**x**&#x200B;以刪除它。

## 編輯條件說明{#section-5015fd2c88ed4b6a95be7f0d53be2db0}

您可以新增說明至新增至篩選器的每個條件。 您可以視需要編輯或移除說明。

>[!NOTE]
>
>只有在「設計篩選」模式下工作時，才會顯示條件說明。

* 以滑鼠右鍵按一下條件，然後按一下&#x200B;**[!UICONTROL Edit description]**。

   * 要添加或編輯說明，請在[!DNL Edit condition description]欄位中鍵入說明。 說明會顯示在篩選器編輯器視窗中條件上方的引號中。

      ![](assets/vis_FilterEditor_ConditionDescription.png)

* 要刪除說明，請按一下&#x200B;**[!UICONTROL Remove description]**。 條件會保留在篩選器編輯器視窗中。
