---
description: 在安裝Insight軟體和數位憑證後，您必須啟動Insight並設定其與Insight Server的連線。
title: 設定與Insight伺服器的連線
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 設定與Insight伺服器的連線{#configuring-the-connection-to-insight-server}

在安裝Insight軟體和數位憑證後，您必須啟動Insight並設定其與Insight Server的連線。

>[!NOTE]
>
>在某些情況下，Adobe諮詢服務或您的系統管理員可能已預先設定與Insight Server的連線。 如果是，則無需完成此任務。

當您第一次啟動Insight時，它會自動連線至Adobe License Server，以註冊您的數位憑證。 要成功完成註冊過程，您必須在執行以下步驟時將電腦連接到Internet。

>[!NOTE]
>
>如果您已依「下載與安裝數位憑證」中所述，要求、下載並安裝預先鎖定的憑證 [](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9),Insight不會嘗試連線至授權伺服器，您也不會收到錯誤訊息。

**若要設定與Insight Server的連線**

在叢集環境中工作時，應將Insight設定為存取主Insight伺服器，以避免同步問題。 在Insight中，您可以使用「伺服器管理器」中 [!DNL Insight Servers] 的功能表項目，來檢視 [!DNL Related Servers] 叢集中處理 [的相關資訊](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-svrs-mgr.html)。

1. 啟動分析。
1. 在上， [!DNL Worktop]按一下 **[!UICONTROL Admin]**，然後 **[!UICONTROL First Steps]**。

1. 按一下縮 **[!UICONTROL Configure Connection to Servers]** 圖。

   此時 [!DNL Servers Manager]將顯 [!DNL Insight.cfg] 示用於配置檔案的 [!DNL Insight.cfg]檔案和說明。

1. 在視窗 [!DNL Insight.cfg] 中，以滑鼠右鍵按一 **[!UICONTROL Servers]** 下並按 **[!UICONTROL Add new child]** > **[!UICONTROL Server]**。

   ![](assets/cfg_Workstation_AddChild.png)

1. 完成或修改伺服器參數，讓Insight可存取您的主Insight伺服器。 如需Insight.cfg檔案中參數的詳細說明，請參閱設定 [參數](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-insght-config-param.html)。

   ![](assets/cfg_Workstation_AddServer.png)

1. 對您要設定連線的每個Insight Server重複步驟4和步驟5。
1. 要保存配置更改，請按一下右鍵 **[!UICONTROL Insight.cfg (modified)]** 窗口頂部的，然後按一下 **[!UICONTROL Save as Insight.cfg]**。

   Insight會嘗試使用您 [!DNL Insight Server(s)] 所指定的設定連線至。 如果建立了連接，則綠色節點將出 [!DNL Servers Manager] 現在中，如下頁所示。

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **綠色：** 指出與Insight伺服器的連線處於作用中。
   * **淺紅色：** 指出伺服器有潛在問題，例如耗用伺服器處理、記憶體使用量高或磁碟空間低。
   * **紅色：** 指出與Insight伺服器的連線未作用中。
   如果Insight無法使用指定的設定進行連線，則會在中顯示紅色節點 [!DNL Servers Manager]。 如果發生這種情況，請參 [閱Connection Troubleshooting](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b)。

<!--
c_dir_crt_setup.xml
-->

當您選取要使用的描述檔時，描述檔資訊（包括相關資料以及為該描述檔定義的任何特定工作區或視覺化）會下載到您的電腦。 當您下載每個描述檔時，Insight會使用描述檔名稱在安裝目錄中建立資料夾。

例如，如果您選取名為Sales的描述檔，則Insight目錄中會出現名為Sales的資料夾。 此資料夾包含在「銷售」描述檔中定義的量度、維度、工作區和視覺化。 在初次載入描述檔後，可在離線工作時使用描述檔。 請參 [閱離線和線上工作](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-off-on.html)。

此外，當您從Insight首次連線至Insight Server時，Insight Server會在Insight安裝目錄中建立下列目錄。

* **[!DNL Trace]目錄：**目錄內[!DNL Trace]是Insight記錄檔([!DNL insight.log])。 當檔案大小達[!DNL Insight.log]到100 MB時，檔案會重新命名為[!DNL insight-1.log]。 如果名稱的檔[!DNL insight-1.log]案已存在，[!DNL insight-1.log]則重新命[!DNL insight-2.log]名為等，最大值為[!DNL insight-9.log]。 該檔案[!DNL insight.log]始終包含最新的日誌資訊，並[!DNL insight-max.log]包含最舊的日誌資訊。

* **[!DNL User]目錄：**目錄中[!DNL User]是與迄今使用的每個配置檔案相對應的資料夾，而每個配置檔案資料夾中都是名為和的[!DNL Work]資料夾[!DNL Workspaces]。 目錄是`User\*profile name*\Workspaces`儲存Insight工作區檔案的預設位置。`User\*profile name*\Work`是Insight視覺化和由Insight使用者執行之其他自訂工作儲存在其預設位置。

下表列出了常用元件的預設位置。

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元件 </th> 
   <th colname="col2" class="entry"> 目錄位置 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>儲存的視覺化 </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>設定檔名稱</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>儲存的工 <span class="wintitle"> 作區</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>描述檔名</i>稱<i>\Workspaces\</i>標籤名稱\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>已儲存<span class="filepath"> .png檔案</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>設定檔名稱</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>資料快取 </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Insight.log</span> 檔案 </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

您可以依索引鍵名稱、索引鍵類型或值來搜尋，以快速找到項目，以免除捲動擴充大型檔案以尋找巢狀資訊的需求。 可以找到維名、伺服器名等。 下列範例顯示片語映射上搜尋的相符項目。

![](assets/cfg_search.PNG)

在此欄位中輸入搜尋片語以找出資料。 欄位的色彩會隨著比對的成功而改變。 相符項目會反白顯示，非相符項目則會暗顯。 如果沒有相符項目，搜尋欄位的背景會變成紅色。 按Enter鍵時，配置樹將展開存在匹配的每個位置，並折疊不匹配的位置。

您也可以在欄位中使用規則運算 [!DNL Search] 式。 例如，您可以使用re:郵 [!DNL *遞區號。*]任何包含&quot;zip&quot;的項目。

要清除搜索，請按 **[!UICONTROL Escape]**。
