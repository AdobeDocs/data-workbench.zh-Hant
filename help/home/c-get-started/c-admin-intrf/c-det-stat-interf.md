---
description: 「詳細狀態」介面對於疑難排解資料工作台伺服器電腦的錯誤或其他問題非常有用。
solution: Analytics
title: 詳細狀態介面
topic: Data workbench
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 詳細狀態介面{#detailed-status-interface}

「詳細狀態」介面對於疑難排解資料工作台伺服器電腦的錯誤或其他問題非常有用。

這包括在這 [!DNL Transform] 些電腦或是「資料工作台」伺 [!DNL Report] 服器用戶端電腦上執行的任何設定檔。 您可以透過功 [!DNL Master Server] 能表 [!DNL Query Server Detailed Status] 存取和介 [!DNL Admin] 面。 要訪問其 [!DNL Detailed Status] 他電腦的介面，請在 [!DNL Servers Manager]中按一下右鍵要查看其狀態的伺服器的節點，然後按一下 **[!UICONTROL Detailed Status]**。 請參 [閱伺服器管理器](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba)。

如需資料工作台伺服器的詳細資訊，請參 *閱伺服器產品安裝與管理指南*。

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>若要更新介面中的資 [!DNL Detailed Status] 訊，請以滑鼠右鍵按一下標 **[!UICONTROL Detailed Status]** 題並按一下 **[!UICONTROL Refresh]**。

下表列出了可使用介面完成的 [!DNL Detailed Status] 任務。

<table id="table_E685F31DCDB343F49FFA1019F2E8DA85"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要執行此任務…… </th> 
   <th colname="col2" class="entry"> 執行動作... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>顯示每個電腦元件及其當前狀態 </p> </td> 
   <td colname="col2"> <p>按一下「 <span class="uicontrol"> 元件狀態</span>」。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>顯示電腦上使用的記憶體量 </p> </td> 
   <td colname="col2"> <p>按一下「 <span class="uicontrol"> Memory Status</span> &gt; <span class="uicontrol"> Address Space Load(記憶體狀態&gt;地址空間載入</span>)」。 </p> <p>有關監視地址空間載入的詳細資訊，請參 <i>閱伺服器產品安裝和管理指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要確定電腦是否配置為使用/3GB交換機 </p> </td> 
   <td colname="col2"> <p>按一下「 <span class="uicontrol"> Memory Status</span> &gt; <span class="uicontrol"> Process Address Space(記憶體狀態&gt;進程地址空間</span>)」。 </p> <p>如果「 <span class="wintitle"> 總計</span> 」欄位顯示超過300000 KB，則您的電腦將配置為使用/3GB交換機。 </p> <p>有關/3GB交換機的詳細資訊，請參 <i>閱伺服器產品安裝和管理指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>監視用於儲存每個維以及用於儲存其元素名稱的磁碟空間和記憶體量 </p> </td> 
   <td colname="col2"> <p>按一下「 <span class="uicontrol"> 效能</span><span class="uicontrol"> &gt;維</span> &gt;磁碟使用量 <span class="uicontrol"> &gt;磁碟使用量</span> &gt;磁碟使用量 <i><span class="uicontrol"></span></i><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><i><span class="uicontrol"></span></i>&gt;效能&lt;配置檔案名&gt;效能&gt;維&gt;記憶體使用量&gt; Memory Memory Usage Jusage &lt;JockProfile Light LightLightS&gt;JockLightPProPNamePProLinProPProPPProPAProProPProPPPProPPProProProProProProProProProProProProProProProProProProProMeProProMeMeMeMeMeMeProProProProMeMeProProProMeMeMeMeMeMeMeMeMeMe </p> <p>「磁 <span class="wintitle"> 盤使用</span> 」欄位提供儲存每個維所需的磁碟空間的名稱和數量(MB)。 大量的磁碟使用量可能會對查詢時間產生負面影響，因為資料工作台伺服器必須讀取所有資料才能完成相關查詢。 降低維的磁碟使用量可以減少完成相關查詢所需的時間。 </p> <p>「記 <span class="wintitle"> 憶體使用</span> 」欄位提供每個維度的元素數量，以及儲存元素名稱清單所需的記憶體量。 大量元素可能會對查詢期間使用的記憶體量產生負面影響，因為資料工作台伺服器必須讀取每個元素。 減少維度中的元素數量可縮短完成相關查詢所需的時間。 </p> <p>範例: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Dimensions&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Disk&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;1.386&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Memory&nbsp;Usage
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;DimensionName&nbsp;21&nbsp;elements,&nbsp;0.001&nbsp;MB
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>監視日誌處理和轉換中各階段的CPU使用情況 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 效能&gt;</span> CPU使用量 <span class="uicontrol"> &gt;</span> CPU使用量 <span class="uicontrol"> &gt;處理日誌&gt;</span> Processing Log Log Or Performance Profication Profile &gt; CPU <i><span class="uicontrol"></span></i><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span>&gt; CPU轉換&gt; Jorting Roduction Log &lt;JunameProfile。 </p> <p>這些欄位集中的每組欄位都提供「日誌處理和轉換」中每個階段的CPU使用量（以秒為單位）。 </p> <p>範例: <code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>完成查詢所需的時間通常與所有維度的總大小成比例。 在檢視每個維度的大小後，您可以評估特定維度是否足夠有用，並且通常足以證明維度的效能成本合理。 否則，可以在「配置檔案管理器」中刪除 <span class="wintitle"> 維</span>。 請參閱<a href="../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-prof-mgr.md"> 「描述檔管理員</a>」。 </p> <p>元素名稱清單過大（即超過128 MB）的維度，即使總位址空間使用量未接近限制，仍可能導致「記憶體不足」錯誤。 </p> <p>此外，如果您使用資料工作台伺服器叢集，但未使用集中式標準化，則元素名稱清單較大的維度會對傳送記憶體預算產生重大影響。 如需集中式標準化的詳細資訊，請參閱資料 <i>集設定指南</i>。 如果儲存所有組合的元素名稱清單所需的記憶體量超過群集中所有伺服器的100 MB，則即使查詢活動很輕，您也可能會收到「超出發送記憶體預算」錯誤。 例如，如果您的四伺服器叢集在每個伺服器上有超過25 MB的儲存元素名稱清單，您可能會收到錯誤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>監視日誌處理和轉換所花費的時間 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 效能&gt;</span> CPU使用量 <span class="uicontrol"> &gt; CPU使用量</span> &gt; <span class="uicontrol"> Processing Log</span> &gt; Processing Name &gt; Performance Profilization Profile Log &gt; CPU使用量 <i><span class="uicontrol"></span></i><span class="uicontrol"></span><span class="uicontrol"></span><span class="uicontrol"></span><i><span class="uicontrol"></span></i>&gt; CPU變換&gt; Ragroming JodProplia。 </p> <p>查看這些部分中的欄位可以識別可能對日誌處理和轉換所需時間產生負面影響的篩選器和轉換。 然後，您就可以針對個別濾鏡和變形做出設計決策，處理時間會很長。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>監視磁碟空間使用情況並提高查詢速度 </p> </td> 
   <td colname="col2"> <p>按一 <span class="uicontrol"> 下「效能</span> &gt;記錄 <span class="uicontrol"> 檔處理欄位</span> &gt; <i>&lt;描述檔名稱<span class="uicontrol"></span></i>&gt;」。 </p> <p>本節中的每個行項目都對應於 <span class="filepath"> Log Processing.cfg檔案中的參數</span> 。 檢閱這些欄位可讓您查看每個參數使用了多少記憶體。 然後，您可以針對個別較大的項目進行設計決策。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要確定先前的重新處理或轉換的經過時間 </p> </td> 
   <td colname="col2"> <p>按一 <span class="uicontrol"> 下處理狀態</span> &gt; <i>&lt;描述檔名稱<span class="uicontrol"> &gt;</span>&gt;</i><span class="uicontrol"></span>模式歷史記錄處理。 </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">即時——資料工作台伺服器可供查詢的時間。 </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">快速輸入——此次加上快速合併時間是處理資料集所需的總時間。 </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">快速合併——轉換資料集所需的總時間。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>診斷「截止時間」問題 </p> </td> 
   <td colname="col2"> <p>按一下「 <span class="uicontrol"> 處理狀態</span> &gt; <i>Profile name<span class="uicontrol"> &gt; &gt;</span>As Processing Status &gt; Profile Name</i><span class="uicontrol"></span><span class="uicontrol"></span>&gt; As Time Sources as-of-Of-Of-Time Sources」。 </p> <p>查看每個源的截止時間有助於確定哪些源可能對「總體截止」產生負面影響。 然後，您就可以解決這些特定來源的問題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要估計運行中的查詢完成所需的時間 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 執行引擎</span>。 </p> <p>查看「 <span class="wintitle"> 資料掃描時間</span> 」欄位可為您提供查詢完成所需時間的估計值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>列出此電腦上所有可用的配置檔案及其狀態的詳細資訊 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 描述檔</span>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看複製狀態 </p> </td> 
   <td colname="col2"> <p>按一下「 <span class="uicontrol"> 元件狀態</span>」。 </p> <p>檢查複製元件的狀態。 如果複製正在運行，則顯示「確定」。 如果複製元件失敗，則顯示一條錯誤消息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>若要檢 <span class="wintitle"> 視連線至</span> 「資料工作台」伺服器之 <span class="keyword"> 「報表</span> 」電腦的「報表伺服器」狀態 </p> </td> 
   <td colname="col2"> <p>按一 <span class="uicontrol"> 下報表伺服器狀態</span>。 </p> <p>「詳細狀態 <span class="wintitle"> 」介面的此區段包含</span><span class="filepath"></span> Report Server.cfg檔案的副本、有關執行中報表數目的資訊（目前切割），以及有關最近錯誤（最後錯誤）的資訊。 </p> <p>如需編輯 <span class="filepath"> Report Server.cfg檔案的步驟</span> ，請參閱資料工 <i>作台報告指南</i>。 </p> <p> <p>注意：如果「 <span class="wintitle"> 報表伺服器狀態</span> 」區段未顯示在「詳細狀態」介面中 <span class="wintitle"> ，您可能需要設定「資料工作台」伺服器以顯示「報表伺服</span> 器狀態」 <span class="wintitle"></span>。 如需步驟，請參閱資 <i>料工作台報表指南</i>。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要查看轉換的記憶體使用資訊，請執行以下操作： </p> </td> 
   <td colname="col2"> <p>按一 <span class="uicontrol"> 下「處理狀態</span> &gt;轉換 <span class="uicontrol"> 」</span>。 </p> <p>有關轉換的詳細資訊，請參 <i>閱《伺服器產品安裝和管理指南</i> 》和 <i>《資料集配置指南》</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>將「詳細 <span class="wintitle"> 狀態</span> 」介面儲存為 <span class="filepath"></span> *.cfg檔案，可在文字編輯器（例如記事本）中開啟或分發給其他人 </p> </td> 
   <td colname="col2"> <p>按一下右鍵「詳細狀 <span class="uicontrol"> 態」標題</span> ，然後按一下 <span class="uicontrol"> 「另存為」</span>。 </p> <p>注意:  <p>按一下右鍵「詳細狀 <span class="uicontrol"> 態</span> 」標題，然後按一下「保存至 <span class="uicontrol"> 伺服器名</span> /狀態/」，在「詳細狀態」介面中 <i></i><span class="wintitle"></span> 不工作。 出現以下錯誤消息： </p> <p>無法保存/Status/。 小行星403 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要查看每 <span class="uicontrol"> 個日誌源度量的行</span> </p> </td> 
   <td colname="col2"> <p>如果「每個記錄檔來源的列」量度需要以「詳細狀態」報告，則資料工作台管理員應定義「記錄檔來源ID」，並在自訂描述檔的Log Processing.cfg中提供唯一名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>

