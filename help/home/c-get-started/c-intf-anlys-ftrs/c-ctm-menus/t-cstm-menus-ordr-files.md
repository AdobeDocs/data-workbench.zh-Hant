---
description: 通過編輯與該菜單關聯的order.txt檔案，可以定制任何菜單的外觀。
solution: Analytics
title: 使用order.txt檔案自訂功能表
topic: Data workbench
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 使用order.txt檔案自訂功能表{#customize-a-menu-using-order-txt-files}

通過編輯與該菜單關聯的order.txt檔案，可以定制任何菜單的外觀。

本節中的步驟適用於所有類型的功能表。

**若要編輯order.txt檔案以自訂功能表**

1. 在的 [!DNL Profile Manager]配置檔案名 *稱列中* ，按一下右鍵檔案的複選標籤 [!DNL order.txt] 並按一下 **[!UICONTROL Make Local]**。
1. 按一下右鍵列中檔案的復 [!DNL order.txt] 選標籤， [!DNL User] 然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。 隨即 [!DNL order.txt] 顯示檔案。

   ![步驟資訊](assets/cfg_ordertxt.png)

1. （可選）視需要 [新增] 或 [] 變更檔案頂端的「包含」或「排除」設定。 此設定會控制功能表中是否列 [!DNL order.txt] 出未列在檔案中但 [!DNL Profile Manager] 存在於中的項目。 選項包括：

   * **[包含]:**這是預設設定。 此設定會導致未在檔案中指定的功能表項[!DNL order.txt]目，以字母順序列在功能表底部。 例如，如果Profile項[!DNL Profile Manager]目中除了上面列出的項目外還包含Profile項目，[!DNL order.txt]Profile將顯示在Data下方。

   * **[獨家]:**此設定會導致未在檔案中指定的功能表項目[!DNL order.txt]被排除在功能表之外。 例如，如果除上[!DNL Profile Manager]面所列項目外還包含一個配置檔案項[!DNL order.txt]目，則菜單中的任何位置都不會顯示配置檔案。

   * **空白：** 如果檔 [案頂端未顯] 示「包含 [」或「排除」,「資料工作台」會顯示功能表項目，就像設定為「包含」] 一樣 []。

1. 完成下列一或多個步驟：

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 要執行此任務…… </th> 
    <th colname="col2" class="entry"> 請執行下列動作... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>重新排序功能表項目 </p> </td> 
    <td colname="col2"> <p>按您希望物料顯示在「資料工作台」中的順序鍵入物料名稱。 </p> <p>例如，只要每個菜單項名稱與其對應的檔案或資料夾名稱匹配，以下內容將導致<b> 「先添加表</b> 」出現，然後 <b>Add Visualization</b>、 <b>Add Legend</b>，最後出現 <b></b> Add Note。 </p> <p><b>新增表格 </b> </p> <p><b>新增視覺化 </b> </p> <p><b>新增圖例 </b> </p> <p><b>新增附註 </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>重新命名功能表項目 </p> </td> 
    <td colname="col2"> <p>在「描述檔管理員」中重新命名相 <span class="wintitle"> 應的檔案或檔案夾</span>，然後變更order.txt檔案中 <span class="filepath"></span> 的項目名稱。 </p> <p>例如，要更名「將注釋添加到新注釋」(Add Annotation to New Annotation)，請更名「 <span class="wintitle"> Profile Manager</span> to New Annotation」（配置檔案管理器）中的「添加註釋」(Add Annotation)資料夾，然後將 <span class="filepath"></span> order.txt檔案中的「添加註釋」(Add Annotation)項目的名稱更改為「新建注釋」(NewAnnotation)。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>隱藏功能表項目 </p> </td> 
    <td colname="col2"> <p>若要隱藏功能表項目，但不要刪除項目本身，請在其名稱的開頭鍵入減號(-)。 </p> <p>例如，下列結果會導致「新增注 <span class="wintitle"> 釋」(Add Annotation</span> )不顯示在功能表中。 </p> <p>新增圖例 </p> <p>-添加註釋 </p> <p>若要再次顯示隱藏的功能表項目，只要移除減號(-)或使用 <span class="filepath"> Insight.cfg檔案中的「取消隱藏全部」參數，請參閱</span> Insight設定參數 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"></a>。 </p> <p>您也可以使用下列方法來隱藏功能表項目： 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>.filter <span class="filepath"> 、</span>.metric <span class="filepath"> 或</span>.dim <span class="filepath"></span> 檔案中的Show參數會從其個別功能表隱藏篩選器、衍生量度和維度以及延伸維度。 使用此選項時，該項目不會列在功能表中，但仍在設定檔中，可供使用。 </p> <p>若要使用此參數來隱藏篩選器和衍生的量度和維度，請在。metric <span class="filepath"> 、</span>.dim <span class="filepath"> 或</span>.filter檔案的結尾加入下列行 <span class="filepath"></span> : </p> <p><span class="filepath"> show = bool:false</span> </p> <p>若要使用此參數來隱藏延伸維度，請參閱資料集設定指南 <i>的第10章</i> ，以取得指示。 </p> <p>您可以透過在 <span class="filepath"> Insight.cfg檔案中設定「取消隱藏全部」參數，暫時取消隱藏使用此方法隱藏的項目</span> 。 如需此參數的詳細資訊，請參閱 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight設定參數</a>。 </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Transformation.cfg檔案或任何資料集中的 <span class="filepath"> Hidden參數</span> ，都會從維度選單中隱藏延伸維度。 使用此選項時，該項目不會列在功能表中，但仍在設定檔中，可供使用。 <p> <p>注意： 使用此方法隱藏延伸維度時，您必須重新轉換資料集，才能隱藏維度。 </p> </p> <p>您可以透過在 <span class="filepath"> Insight.cfg檔案中設定「取消隱藏全部」參數，暫時取消隱藏使用此方法隱藏的項目</span> 。 如需此參數的詳細資訊，請參閱 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight設定參數</a>。 </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>零位元組檔案會隱藏任何功能表上的任何類型項目。 使用此選項時，空的（零位元組）檔案會隱藏包含資料的同名檔案。 資料工作台將零位元組檔案視為不存在。 如需詳細資訊，請 <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> 參閱使用空（零位元組）檔案隱藏檔案</a>。 </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>刪除功能表項目 </p> </td> 
    <td colname="col2"> <p>如果此檔案設定為使用[Exclusive]選項，則只需從此檔案中刪除菜單項即可。 項目本身仍在描述檔中，但未列在功能表中。 </p> <p>如果此檔案設定為使用[Inclusive]選項，則必須從此檔案中刪除菜單項名稱，然後刪除或零位元組刪除相應檔案以從菜單中刪除該項。 </p> <p>有關刪除檔案的資訊，請參 <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> 閱從工作配置檔案中刪除檔案</a>。 有關零位元組檔案的資訊，請參 <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> 閱使用空（零位元組）檔案隱藏檔案</a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>新增群組標題 </p> </td> 
    <td colname="col2"> <p>在要顯示的標題文字前後鍵入三個連字型大小。 </p> <p>例如，下列項目會產生一組相關功能表項目的「管理」群組標題。 </p> <p>---管理--- </p> <p>描述檔 </p> <p>資料集 </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>在功能表的個別區段中新增一行 </p> </td> 
    <td colname="col2"> <p>鍵入三個連字型大小，以便顯示一行。 </p> <p>例如，下列結果會產生一行分隔「新增附註」和「新增自訂」。 </p> <p>添加註釋 </p> <p>--- </p> <p>新增自訂 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 儲存並關閉檔案。
1. （可選）要讓所有使用者都能使用工作設定檔的變更，請在欄中以滑鼠右鍵按一下檔案的 [!DNL order.txt] 白色核取 [!DNL User] 標籤，然後按 **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**
