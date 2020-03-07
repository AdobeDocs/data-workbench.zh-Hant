---
description: 資料工作台6.2版本注意事項包括新功能、升級需求、錯誤修正和已知問題。
title: 資料工作台6.1發行說明
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Data Workbench 6.2 Release Notes{#data-workbench-release-notes}

資料工作台6.2版本注意事項包括新功能、升級需求、錯誤修正和已知問題。

## 新功能 {#section-1225066ea8f44cf68e42e019d0bca816}

Data Workbench 6.2包含下列新功能：

| 功能 | 說明 |
|--- |--- |
| Decision Trees | 決策樹是預測性分析視覺化，用來評估訪客特性和關係。 決策樹建立工具可以根據指定的正面案例和一組想法產生決策樹視覺化效果。 |
| 關聯矩陣中二進位濾波器的更新 | 「二進位篩選」已更新為新功能，您必須使用舊版中建立的二進位篩選來重建任何關聯矩陣。 |
| 密度圖 | 密度圖是視覺化，在方形圖中將元素顯示為陰影矩形。 |
| 歸因設定檔 | 為快速分析歸因值（成功轉換或銷售的歸因責任事件），資料工作台提供以規則為基礎的歸因描述檔，其中包含建築師設定歸因報表和分析師執行報表的功能。 |
| 分析報表 | 報表範本會為使用Adobe SC設定檔的資料工作台使用者標準化Adobe Analytics的報表。 這些報表與「行銷報告與分析」（舊稱SiteCatalyst）中採用的報表相同。 |
| 3D散布圖 | 3D散布圖會在三維格線上繪製資料維度（例如天數或反向連結網站）的元素，其中x、y和z軸代表各種度量。 |


## 資料工作台用戶端UI更新{#data-workbench-client-ui-updates}

資料工作台6.2包含書籤面板的新使用者介面更新、工作區工具列中的新圖示、在螢幕內拖曳工作區的功能、新的快速鍵，以及圓形圖視覺化的更新。

## 新書籤功能 {#section-e361b605441540ca8213c3fddb5e0718}

您現在可以為重要工作區建立書籤，以便在工作流程中採用的視覺化和報表之間快速移動。

**使用書籤**

1. 按一下工具列右上角的「書 ![](assets/bookmark_icon.png) 簽」圖示，將工作區加入書籤。
1. 按一 **[!UICONTROL Add]** 下左 **[!UICONTROL Bookmarks Panel]** 窗格中的>以開啟書籤清單。

   ![](assets/bookmarks_panel.png)

1. 若要開啟書籤化工作區，請按一下中的工作區名稱 **[!UICONTROL Bookmark Panel]**。

   ![](assets/bookmarks_panel_left.png)

   將會開啟選定的工作區。 當您按一下其他書籤化工作區時，上一個工作區將會關閉，而新選取的工作區將會開啟，讓您可以快速導覽工作流程。

**若要刪除書籤：**

* 在「書籤」面板中，按一下滑鼠右鍵並選取「移除」 **[!UICONTROL 。<bookmark title>]**刪除選定的書籤，或選擇刪&#x200B;**[!UICONTROL Clear All Bookmarks]**除所有書籤。

* 您也可以在工作台的縮圖檢視中，以滑鼠右鍵按一下工作區，然後選取 **[!UICONTROL Clear Bookmark]**。

>[!IMPORTANT]
>
>* 可儲存25個書籤。
>* 如果您新增書籤，然後移動工作區的位置，書籤將無效，且必須從「書籤面板」中刪除並重設。
>



## 工作區中的新圖示 {#section-c108bbd1661249e79c146727ff3d2470}

資料工作台6.2現在會以圖示取代工作區中的文字。 您仍可將滑鼠指標暫留在上方，並查看識別圖示的工具提示訊 **[!UICONTROL File]**&#x200B;息， **[!UICONTROL Add]**&#x200B;包括、 **[!UICONTROL Export]**&#x200B;和。

![](assets/new_icons.png)

會新增 **[!UICONTROL Help]** 一個圖示來存取檔案和其他知識中心，包括下列連結：

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 檔案連結 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 行銷 Reports &amp; Analytics </td> 
   <td colname="col2">開啟至 <span class="uicontrol"> Adobe行銷報告與分析說明頁面</span> 。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Idea Exchange </td> 
   <td colname="col2">開啟至 <span class="uicontrol"> Idea Exchange登入</span>。 此線上入口網站可讓使用者為資料工作台提供更新變更和增強概念。 然後，所有使用者都可以投票決定這些以客戶為中心的想法。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 說明 </td> 
   <td colname="col2">開啟「資 <span class="uicontrol"> 料工作台」檔案</span>。 <p>您也可以按 <span class="uicontrol"> &lt;F1&gt;</span> ，在工作區中開啟說明。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 關於 </td> 
   <td colname="col2">開啟以識別資 <span class="uicontrol"> 料工作台</span> 的用戶端版本。 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>您也可以按 `<F1>` 鍵從工作區開啟檔案。

## 拖曳工作區檢視 {#section-9129c340c21d45a3864c923884cd4382}

如果工作區大於可查看的螢幕，則可以移動視圖以查看工作區中的所有元素。 您可以按一下背景（視覺化和表格以外），然後拖曳畫面，在工作區中移動可檢視區域。 在工作區框架中拖動視圖時，游標將變為手形表徵圖。

![](assets/drag_workspace.png)

## 變更工作區檢視的快速鍵 {#section-d8322f72423f437aa2e34f2188b1341c}

新的快速鍵可讓您調整視窗和完整頁面檢視之間的工作區大小並重新調整其大小。

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 命令 </th> 
   <th colname="col2" class="entry"> 快速鍵 </th> 
   <th colname="col3" class="entry"> 組合的菜單命令 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>全螢幕檢視</b>。 工作區會填滿螢幕並重新調整為新大小。 </td> 
   <td colname="col2"><b>Ctrl +</b> <p>Ctrl +（在鍵盤上） </p> <p><i>或</i> </p> <p>Ctrl Shift +（在鍵盤上） </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">「檔案&gt;頁面大小&gt;填滿螢幕」 <p><i>後跟</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">「檔案&gt;重新調整工作區」 </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>窗口視圖</b>。 工作區會顯示在標準視窗檢視中，並重新調整為新大小。 </td> 
   <td colname="col2"><b>Ctrl減號</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">「檔案&gt;頁面大小&gt;標準」 <p><i>後跟</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">「檔案&gt;重新調整工作區」 </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## 錯誤修正 {#section-8704a9ac358246cd81233dd0982d534f}

* 更新「視覺化網站查閱」檔案，以處理搜尋引擎對查詢搜尋詞所做的變更。
* 修正即使匯入成功，在用戶端工作站中匯入工作區時，仍會顯示「無法匯入工作區」的錯誤訊息。
* 顯示「412配置衝突」消息的工作站連接錯誤現在被標識系統操作的用戶友好消息替換。
* 現已可在報表伺服器中執行 &quot;post&quot; 命令。
* 修正用戶端使用者介面的簡體中文使用者介面錯誤。
* Adobe Analytics更新了資料饋送，讓資料工作台能夠運用與Adobe Experience Cloud整合的設定檔和觀眾。 所有資料工作台使用者都必須在2014年4月21日之前為此轉場準備環境。

   「個人檔案與觀眾」是為了提供Adobe Analytics客戶的完整檢視。 Adobe Experience Cloud中提供這項新服務，可進一步提升分析工具的價值，以開始為Analytics中的這些功能奠定基礎。 新的Experience Cloud訪客識別碼將會新增至資料饋送，以及其他增強功能和改進，以配合新的資料饋送和全域訪客識別碼。
* 匯入工作區時，即使匯入成功，仍會顯示錯誤訊息。

## 升級需求 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* 「歸因」描述檔是為已實作Adobe SC描述檔以採用Analytics(SC/Insight)資料饋送的使用者所設定。 依預設，行銷和轉換事件會作為在規則型模型中評估的預設互動。
* 對於升級至Data Workbench 6.2的Adobe SC設定檔使用者，如果您未使用預設設定，請確認檔案中的 [!DNL x-bot_id][!DNL SC Fields.cfg] 值已正確解碼，以及 [!DNL x-bot_id] 欄位已正確列在 [!DNL Decoding Instructions.cfg] 和檔 [!DNL Exclude Hit.cfg] 案中。 只有在從預設配置中修改配置檔案時，才會出現此問題。

* 如果您已刪除Adobe SC描述檔的 **[!UICONTROL Dataset]** > **[!UICONTROL記錄檔處理****[!DNL SC Fields.cfg]** >檔案中未使用的欄位，您將需要更新以容納用於Attribution描述檔的更新欄位值。

## 已知問題 {#section-dbb307639835493a83409f5f461932b8}

* 當3D散布圖視覺化包含圖說時，縮放會在視覺化的邊框外顯示圖畫。

   解決方法：先縮放3D散布圖，然後將圖說加入視覺化。
* 將量度從「尋找者」面板拖曳至量度欄外的「量度圖例」，將會從工作區中刪除「量度圖例」。

   解決方法：想要將量度拖曳至量度圖例的使用者，應將其拖曳至第一欄（量度欄）。
* 使用側欄和兩者選項的列印工作區將不包含列印頁面上的著作權資訊。
* 更名工作區時，在遠程案頭會話中使用工作站將崩潰。
* （簡體中文版）實際報表輸出在報表伺服器中有效，但電子郵件主旨行和附件檔案名稱會亂碼。
* （簡體中文版）在「工作表」視覺化中使用換行文字時，無法正確換行本地化字詞，導致無用字元新增至字串。
* （簡體中文版）如果安裝目錄的名稱為非英文字元，則無法啟動Insight.exe。

   解決方法：在資料夾路徑中僅使用英文字元保留預設名稱或更名，以啟動執行檔。

