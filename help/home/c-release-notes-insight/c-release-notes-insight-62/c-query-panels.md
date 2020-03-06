---
description: 使用資料工作台中的Finder面板來選取量度、維度和篩選。 這些面板提供搜尋支援、排序選項以及拖放功能。
solution: Analytics
title: 尋找工具
topic: Data workbench
uuid: 7a4144f5-133f-48ed-9613-1e42b1313120
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 尋找工具{#finders}

使用資料工作台中的Finder面板來選取量度、維度和篩選。 這些面板提供搜尋支援、排序選項以及拖放功能。

Finder面板可在左側邊欄或工作區中開啟。

![](assets/query_entity_panel_main.png)

<table id="table_3E43DBA0646842898F14F31374F9E39C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 維度搜尋器 </th> 
   <th colname="col2" class="entry"> 量度搜尋器 </th> 
   <th colname="col3" class="entry"> 篩選器搜尋器 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>查詢模型中所有維的清單。 </p><img placement="break" id="image_D7D317D84C0843BE8D324E5B9F7AF20D" src="assets/query_entity_dim_panel.png" /> </td> 
   <td colname="col2"> <p>查詢模型中所有度量的清單。 </p><img placement="break" id="image_04553B2F2C6A48FE897B4EFF002BED59" src="assets/query_entity_metric_panel.png" /> </td> 
   <td colname="col3"> <p>為您的組織建立的所有篩選清單。 </p><img placement="break" id="image_920E72D795644634A82D1955CB64B355" src="assets/query_entity_filters_panel.png" /> </td> 
  </tr> 
 </tbody> 
</table>

**若要開啟Finder:**

* 在工作區中按一下滑鼠右鍵，然後選取 **[!UICONTROL Tools]** > **[!UICONTROL Finder]**。

   「搜尋器」窗格會在工作區中開啟，其中包含「量度」、「維度」和「篩選器」的標籤。

* 在左側邊欄中按一下滑鼠右鍵，然後選取 **[!UICONTROL Add]** > **[!UICONTROL Finder]**。

   「搜尋器」窗格將在左側面板中開啟。

Finder **包含** 下列功能：

<table id="table_072047E919204577AE85789BAE0F4EE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Finder功能 </th> 
   <th colname="col2" class="entry"> 詳細資料 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>拖放</b> </td> 
   <td colname="col2"> <p> 您可以從面板將維度或度量拖放至工作區中的視覺化，以變更維度或新增度量。 </p> 
    <ol id="ol_612DC76EC04C4FCE938B20B388C43CE8"> 
     <li id="li_7F73B781141E4B8CAE9800F580F62E44">按住 <span class="uicontrol"> &lt;Ctrl&gt;和</span> &lt;Alt&gt;鍵 <span class="uicontrol"></span> ，然後從「搜尋器」面板中選取維度或量度。 </li> 
     <li id="li_631D57976F71415AA61F33EBBFDD128A">從窗格拖曳新維度並拖曳至視覺化，以變更或新增維度。 </li> 
     <li id="li_5329FB82225F46EBBE3A996A641058DE">若要新增量度，請從窗格拖曳新量度，並將其拖曳至選取視覺化的量度標題。 </li> 
    </ol> <p>這適用於所有相關的視覺化，包括表格、訪客叢集、關聯矩陣、散布圖和2-D長條圖（視軸而定）。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>搜尋</b> </td> 
   <td colname="col2">「尋 <span class="uicontrol"> 找器</span> 」面板中的「搜尋」方塊可讓您篩選維度、量度和篩選器的名稱。 
    <ul id="ul_0F6F377E9906472E99008EBE7483F689"> 
     <li id="li_75857895EDB045C8B2960393854B257D"> <p>模式比對（簡單的全域搜尋）。 開始在「搜尋」欄位中輸入必要維度、量度或篩選實體的名稱，而且只有名稱中任何位置包含的相符字串才會被篩選並顯示在「尋找者」窗格中。 </p> <p>例如，輸入： </p> <code><b>Search:</b>click</code> <p>您可以在「維度搜尋器」中取得下列結果： </p> <p><img placement="break" id="image_7CBAAABA92BB47658B7F9F5C0263CF20" src="assets/finders_glob_search.png" /> </p> <p>標準模式比對可讓您使用萬用字元，例如。 (dot), "?" 、和"*"（星號）。 </p> </li> 
     <li id="li_044F9EC1399B44CD81E1852F85137704"> <p>規則運算式。 另外，還支援更複雜的規則運算式來新增搜尋功能。 將首碼"re:"新增至搜尋詞前面（無空格），以解譯為規則運算式。 </p> <p>例如，輸入： </p> <code><b>Search:</b>re.*ip</code> <p>您可以在「維度搜尋器」中取得下列結果： </p> <p><img placement="break" id="image_F47DB90B36504997AA1C509855B89A47" src="assets/finders_regex_search.png" /> </p> </li> 
    </ul> <p>如需深入的搜尋資訊，請參閱規 <a href="https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-reg-exp.html" format="http" scope="external"> 則運算式</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>維類型</b> </td> 
   <td colname="col2">在「維」頁籤中，可以按一下右鍵頁籤標題，按維類型排序。 <p><img id="image_FB44D0F4D36B4AD7A6165E0432211AB6" placement="break" src="assets/query_entity_search_types.png" /> 
     <ul id="ul_D36B8474730F4859BC7AA015CC1B8EF0"> 
      <li id="li_4AE1D5699D0E45AF880A134F886B8B19">屬性——根據訪客、產品、地理位置、時間、視訊和其他屬性的特性建立的維度。 </li> 
      <li id="li_0B2A08F8CBE94356AC506F95DC268C47">群集——在群集生成器中構建的維。 </li> 
      <li id="li_4BC3396A680B49A4B6BDAAD066826864">分數——在傾向分數內建立的維度。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>標籤</b> </td> 
   <td colname="col2">在每個標籤中，您可以按一下滑鼠右鍵並選取「標籤 <span class="uicontrol"></span> 」，以重新命名Finder窗格。 <p><img placement="break" id="image_F61C57F6548646069242DFB2490C67B9" src="assets/label_change.png" /> </p> <p>預設的「維度」、「量度」和「篩選」標籤可變更為符合您組織慣例的標籤名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>新增項目</b> </td> 
   <td colname="col2">在每個標籤中，您可以按一下滑鼠右鍵並選取「 <span class="uicontrol"> 新增項目</span> 」，以開啟表格並手動新增維度、量度和篩選。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>尋找工具列</b> </td> 
   <td colname="col2">在左側邊欄的 <span class="uicontrol"> Finders</span> bar中按一下滑鼠右鍵，以開啟其他功能的選單。 <p><img placement="break" id="image_4DA4930294B84308A1E627C828C35663" src="assets/finders_menu.png" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Close</b> </td> 
   <td colname="col2">在「尋找者」列中按一 <span class="uicontrol"> 下滑鼠右鍵</span> ，然後選取「關閉 <span class="uicontrol"></span> 」以關閉「尋找者」窗格。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>儲存</b> </td> 
   <td colname="col2">在標題列中按一下滑鼠右鍵並選取「儲存」選項，將清單儲存在本機 <span class="uicontrol"> 中</span> 。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>匯出</b> </td> 
   <td colname="col2">您可以從Finder面板匯出選取的維度、量度或篩選器清單，方法是在尋找工具列中按一下滑鼠右鍵，然後從功能表選取「匯 <span class="uicontrol"> 出</span> 」。 <p> 新增名稱並匯出至Microsoft Excel。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>複製</b> </td> 
   <td colname="col2"> 複製維度、量度或篩選器的清單。 您可以以檔案或圖形的形式複製為深色背景、淺色背景或單色。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>最小化</b> </td> 
   <td colname="col2"> 最小化Finder窗格。 將只顯示查找器條。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>無邊框</b> </td> 
   <td colname="col2"> 在工作區中（但在左側邊欄中）顯示沒有尋找者邊框的窗格。 </td> 
  </tr> 
 </tbody> 
</table>

