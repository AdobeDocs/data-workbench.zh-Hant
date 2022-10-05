---
description: 您可以編輯與該功能表相關聯的order.txt檔案，以自訂任何功能表的外觀。
title: 使用 order.txt 檔案自訂功能表
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
exl-id: 3803a56f-19b7-4792-a277-97f76c11ec0e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 2%

---

# 使用 order.txt 檔案自訂功能表{#customize-a-menu-using-order-txt-files}

{{eol}}

您可以編輯與該功能表相關聯的order.txt檔案，以自訂任何功能表的外觀。

本節中的步驟適用於所有類型的菜單。

**若要編輯order.txt檔案以自訂功能表**

1. 在 [!DNL Profile Manager]，在 *設定檔名稱* 欄，按一下右鍵 [!DNL order.txt] 按一下 **[!UICONTROL Make Local]**.
1. 以滑鼠右鍵按一下 [!DNL order.txt] 檔案 [!DNL User] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. 此 [!DNL order.txt] 檔案。

   ![步驟資訊](assets/cfg_ordertxt.png)

1. （選用）新增或變更 [包含] 或 [獨家] 設定（如果需要）。 此設定會控制 [!DNL order.txt] 檔案，但存在於 [!DNL Profile Manager] 會顯示。 選項包括：

   * **[包含]:** 這是預設設定。 此設定會產生未在 [!DNL order.txt]檔案，按字母順序列在菜單底部。 例如，若 [!DNL Profile Manager] 除了 [!DNL order.txt] 如上所示，設定檔會顯示在資料下方。

   * **[獨家]:** 此設定會產生未在 [!DNL order.txt] 檔案。 例如，若 [!DNL Profile Manager] 除了 [!DNL order.txt] 上方，設定檔不會顯示在功能表的任何位置。

   * **空白：** 若兩者皆非 [包含] 或 [獨家] 顯示在檔案頂端，Data Workbench會以設定為的方式顯示功能表項目 [包含].

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
    <td colname="col1"> <p>重新排序菜單項 </p> </td> 
    <td colname="col2"> <p>按您希望項目名稱在Data Workbench中顯示的順序鍵入項目名稱。 </p> <p>例如，只要每個菜單項名稱與其對應的檔案或資料夾名稱匹配，則以下項將導致<b> 新增表格</b> 先顯示，然後 <b>新增視覺效果</b>, <b>添加圖例</b>，和 <b>添加註釋</b> 最後顯示。 </p> <p><b>新增表格 </b> </p> <p><b>新增視覺效果 </b> </p> <p><b>添加圖例 </b> </p> <p><b>添加註釋 </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>重新命名功能表項目 </p> </td> 
    <td colname="col2"> <p>重新命名 <span class="wintitle"> 設定檔管理員</span>，然後變更 <span class="filepath"> order.txt</span> 檔案。 </p> <p>例如，要將「添加註釋」更名為「新注釋」，請更名 <span class="wintitle"> 設定檔管理員</span> 新注釋，然後更改 <span class="filepath"> order.txt</span> 檔案到新注釋。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>隱藏菜單項 </p> </td> 
    <td colname="col2"> <p>若要隱藏功能表項目，但不要刪除項目本身，請在其名稱的開頭鍵入減號(-)。 </p> <p>例如，下列結果會產生 <span class="wintitle"> 添加註釋</span> 未出現在功能表中。 </p> <p>添加圖例 </p> <p> — 添加註釋 </p> <p>若要再次顯示隱藏的功能表項目，只需移除減號(-)，或使用 <span class="filepath"> Insight.cfg</span> 檔案，請參閱 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> 分析設定參數</a>. </p> <p>您也可以使用下列方法來隱藏功能表項目： 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>中的Show參數 <span class="filepath"> .filter</span>, <span class="filepath"> .metric</span>，或 <span class="filepath"> .dim</span> 檔案會從各自的功能表中隱藏篩選器、衍生量度和維度以及延伸維度。 使用此選項時，功能表中不會列出項目，但項目仍在設定檔中且可供使用。 </p> <p>若要使用此參數來隱藏篩選器以及衍生的量度和維度，請在 <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span>，或 <span class="filepath"> .filter</span> 檔案： </p> <p><span class="filepath"> show = bool:false</span> </p> <p>若要使用此參數來隱藏延伸維度，請參閱 <i>資料集組態指南</i> 的說明。 </p> <p>您可以透過在 <span class="filepath"> Insight.cfg</span> 檔案。 如需此參數的詳細資訊，請參閱 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> 分析設定參數</a>. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">中的隱藏參數 <span class="filepath"> Transformation.cfg</span> 檔案或任何包含資料集的檔案會從「維度」功能表中隱藏延伸維度。 使用此選項時，功能表中不會列出項目，但項目仍在設定檔中且可供使用。 <p> <p>注意：使用此方法隱藏延伸維度時，您必須重新轉換資料集才能隱藏維度。 </p> </p> <p>您可以透過在 <span class="filepath"> Insight.cfg</span> 檔案。 如需此參數的詳細資訊，請參閱 <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> 分析設定參數</a>. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>零位元組檔案隱藏任何菜單上的任何類型的項目。 使用此選項時，空的（零位元組）檔案會隱藏包含資料且名稱相同的檔案。 Data Workbench將零位元組檔案視為不存在。 如需詳細資訊，請參閱 <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> 使用空（零位元組）檔案隱藏檔案</a>. </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>刪除菜單項 </p> </td> 
    <td colname="col2"> <p>如果此檔案設定為使用[獨佔]選項，則只需從此檔案中刪除菜單項即可。 項目本身仍在設定檔中，但未列在功能表中。 </p> <p>如果將此檔案設定為使用[包含]選項，則必須從此檔案中刪除菜單項名，並刪除相應檔案，或將相應檔案設為零位元組，以從菜單中刪除該項。 </p> <p>有關刪除檔案的資訊，請參閱 <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> 從工作設定檔刪除檔案</a>. 有關零位元組檔案的資訊，請參見 <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> 使用空（零位元組）檔案隱藏檔案</a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>新增群組標題 </p> </td> 
    <td colname="col2"> <p>在要顯示的標題文字之前和之後輸入三個連字型大小。 </p> <p>例如，下列項目會產生一組相關功能表項目的「管理」群組標題。 </p> <p>---管理--- </p> <p>設定檔 </p> <p>資料集 </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>新增一行以區隔功能表的區段 </p> </td> 
    <td colname="col2"> <p>輸入三個連字型大小，以顯示行。 </p> <p>例如，以下結果將「添加註釋」(Add Annotation)和「添加自定義」(Add Custom)分開一行。 </p> <p>添加註釋 </p> <p>— </p> <p>新增自訂 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 儲存並關閉檔案。
1. （可選）若要讓變更可供工作設定檔的所有使用者使用，請以滑鼠右鍵按一下 [!DNL order.txt] 檔案 [!DNL User] 欄，按一下 **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
