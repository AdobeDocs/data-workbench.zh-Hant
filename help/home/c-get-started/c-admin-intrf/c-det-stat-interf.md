---
description: 「詳細狀態」介面對於診斷Data Workbench伺服器電腦的錯誤或其他問題非常有用。
title: 詳細狀態介面
uuid: c4d375d9-431f-4b0a-ba15-b7a10501b2e2
exl-id: 6a460ebd-fb8f-4486-9849-dad2ff745cb5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1223'
ht-degree: 0%

---

# 詳細狀態介面{#detailed-status-interface}

{{eol}}

「詳細狀態」介面對於診斷Data Workbench伺服器電腦的錯誤或其他問題非常有用。

包括任何 [!DNL Transform] 在這些電腦上運行的配置檔案，或 [!DNL Report] 作為Data Workbench伺服器的客戶端的電腦。 您可以存取 [!DNL Master Server] 和 [!DNL Query Server Detailed Status] 介面 [!DNL Admin] 功能表。 若要存取 [!DNL Detailed Status] 介面，位於 [!DNL Servers Manager]，按一下右鍵要查看其狀態的伺服器節點，然後按一下 **[!UICONTROL Detailed Status]**. 請參閱 [伺服器管理員](../../../home/c-get-started/c-admin-intrf/c-svrs-mgr.md#concept-2dfff1ca5bce470a8ee854ed57cbe5ba).

如需Data Workbench伺服器的詳細資訊，請參閱 *《伺服器產品安裝與管理指南》*.

![](assets/vis_DetailedStatus.png)

>[!NOTE]
>
>更新 [!DNL Detailed Status] 介面，按一下右鍵 **[!UICONTROL Detailed Status]** 標題和按一下 **[!UICONTROL Refresh]**.

下表列出可使用 [!DNL Detailed Status] 介面。

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
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 元件狀態</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>顯示電腦上使用的記憶體 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 記憶體狀態</span> &gt; <span class="uicontrol"> 地址空間負載</span>. </p> <p>有關監視地址空間負載的詳細資訊，請參見 <i>《伺服器產品安裝與管理指南》</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>確定電腦是否配置為使用/3GB交換機 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 記憶體狀態</span> &gt; <span class="uicontrol"> 進程地址空間</span>. </p> <p>若 <span class="wintitle"> 總計</span> 欄位顯示的內容超過3000000 KB，則您的電腦配置為使用/3GB交換機。 </p> <p>有關/3GB交換機的詳細資訊，請參見 <i>《伺服器產品安裝與管理指南》</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>監視用於儲存每個維的磁碟空間和記憶體量，以及用於儲存其元素名稱的磁碟空間和記憶體量 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 效能</span> &gt; <span class="uicontrol"> Dimension</span> &gt; <span class="uicontrol"> 磁碟使用情況</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt; </i>或 <span class="uicontrol"> 效能</span> &gt; <span class="uicontrol"> Dimension</span> &gt; <span class="uicontrol"> 記憶體使用量</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i>. </p> <p>此 <span class="wintitle"> 磁碟使用情況</span> 欄位提供儲存每個維度所需的磁碟空間名稱和數量（以MB為單位）。 大量磁碟使用量可能會對查詢時間產生負面影響，因為Data Workbench伺服器必須讀取所有資料以完成相關查詢。 降低維的磁碟使用量可以減少完成相關查詢所花費的時間。 </p> <p>此 <span class="wintitle"> 記憶體使用量</span> 欄位會提供每個維度中的元素數量，以及儲存元素名稱清單所需的記憶體量。 大量元素可能會對查詢期間使用的記憶體量產生負面影響，因為Data Workbench伺服器必須讀取每個元素。 減少維度中的元素數量可縮短完成相關查詢所需的時間。 </p> <p>範例：<code>+&nbsp;Performance
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
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 效能</span> &gt; <span class="uicontrol"> CPU使用量</span> &gt; <span class="uicontrol"> 記錄處理</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i> 或 <span class="uicontrol"> 效能</span> &gt; <span class="uicontrol"> CPU使用量</span> &gt; <span class="uicontrol"> 轉換</span> &gt; &lt;<span class="uicontrol"> 設定檔名稱</span>&gt;。 </p> <p>這些欄位集中的每一個欄位都提供「日誌處理和轉換」中各階段的CPU使用量（以秒為單位）。 </p> <p>範例：<code>+&nbsp;Performance
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;CPU&nbsp;Usage&nbsp;
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;ProfileName&nbsp;158.9&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Built-in&nbsp;158.1&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;13.0&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;.&nbsp;.&nbsp;.
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;Log&nbsp;Processing\ProfileName&nbsp;0.8&nbsp;sec
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;-&nbsp;StageName&nbsp;0.8&nbsp;sec</code> </p> <p>完成查詢所需的時間通常與所有維度的總大小成比例。 檢閱每個維度的大小後，您可以評估特定維度是否足夠有用，且經常使用到足以證明維度的效能成本合理的維度。 若非如此，您可以在 <span class="wintitle"> 設定檔管理員</span>.<p>元素名稱清單過大（即超過128 MB）的維可能會導致「記憶體不足」錯誤，即使總地址空間使用量不接近限制。 </p> <p>此外，如果您使用的是Data Workbench伺服器群集，但未使用集中標準化，則元素名稱清單很大的維會對傳送記憶體預算產生重大影響。 如需集中標準化的詳細資訊，請參閱 <i>資料集組態指南</i>. 如果儲存群集中所有伺服器上所有合併的元素名稱清單所需的記憶體量超過100 MB，則即使查詢活動很輕，您也可能收到「超出傳送記憶體預算」錯誤。 例如，如果您的四伺服器叢集每個伺服器上都有超過25 MB的儲存元素名稱清單，您可能會收到錯誤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>監控記錄處理和轉換所花費的時間 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 效能</span> &gt; <span class="uicontrol"> CPU使用量</span> &gt; <span class="uicontrol"> 記錄處理</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i> 或 <span class="uicontrol"> 效能</span> &gt; <span class="uicontrol"> CPU使用量</span> &gt; <span class="uicontrol"> 轉換</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i>. </p> <p>檢閱這些區段中的欄位，即可識別可能對記錄處理和轉換所需的時間長度造成負面影響的篩選器和轉換。 然後，您可以針對個別篩選器和轉換進行設計決策，處理時間會很長。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>監視磁碟空間使用情況並提高查詢速度 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 效能</span> &gt; <span class="uicontrol"> 記錄處理欄位</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i>. </p> <p>此區段中的每個條列項目都與 <span class="filepath"> Log Processing.cfg</span> 檔案。 檢閱這些欄位可讓您查看每個參數使用的記憶體大小。 然後，您就可以針對個別較大的項目進行設計決策。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>判斷先前重新處理或轉換的經過時間 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 處理狀態</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i> &gt; <span class="uicontrol"> 處理模式歷史記錄</span>. </p> <p> 
     <ul id="ul_B7CC0DF54E004C72B220F928CF223F8E"> 
      <li id="li_2707D8C0D52A44C8BADA4D9AFB5EB2BC">即時 — Data Workbench伺服器可用於查詢的時間。 </li> 
      <li id="li_3A3B490D70864A259780FC9FFC9AC15E">「快速輸入」 — 此次加上「快速合併」時間，即為處理資料集所需的總時間。 </li> 
      <li id="li_B754C6DECD924170A15721EA4C942E3D">快速合併 — 轉換資料集所需的總時間。 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>診斷「截止時間」問題 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 處理狀態</span> &gt; <i>&lt;<span class="uicontrol"> 設定檔名稱</span>&gt;</i> &gt; <span class="uicontrol"> 截止時間</span> &gt; <span class="uicontrol"> 來源截止</span>. </p> <p>查看每個源的截止時間有助於確定哪些源可能對整體截止時間產生負面影響。 然後，您可以解決這些特定來源的問題。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要估計運行的查詢需要多長時間才能完成 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 執行引擎</span>. </p> <p>檢閱 <span class="wintitle"> 資料掃描時間</span> 欄位提供查詢完成所需時間的預估值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>列出此電腦上所有可用的配置檔案及其狀態的詳細資訊 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 設定檔</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看複製狀態 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 元件狀態</span>. </p> <p>檢查複製元件的狀態。 如果複製正在運行，則顯示「確定」。 如果複製元件失敗，則會顯示錯誤消息。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要查看 <span class="wintitle"> 報表伺服器</span> 狀態 <span class="keyword"> 報表</span> 連接到Data Workbench伺服器的電腦 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 報表伺服器狀態</span>. </p> <p>此部分 <span class="wintitle"> 詳細狀態</span> 介麵包含 <span class="filepath"> Report Server.cfg</span> 檔案、正在運行的報表數的相關資訊（當前片），以及有關最近錯誤的資訊（上一個錯誤）。 </p> <p>編輯 <span class="filepath"> Report Server.cfg</span> 檔案，請參閱 <i>Data Workbench報表指南</i>. </p> <p> <p>注意：若 <span class="wintitle"> 報表伺服器狀態</span> 區段不會顯示在 <span class="wintitle"> 詳細狀態</span> 介面，您可能需要將Data Workbench伺服器設定為顯示 <span class="wintitle"> 報表伺服器狀態</span>. 如需步驟，請參閱 <i>Data Workbench報表指南</i>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>查看轉換的記憶體使用資訊 </p> </td> 
   <td colname="col2"> <p>按一下 <span class="uicontrol"> 處理狀態</span> &gt; <span class="uicontrol"> 轉換</span>. </p> <p>如需轉換的詳細資訊，請參閱 <i>《伺服器產品安裝與管理指南》</i> 和 <i>資料集組態指南</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>若要儲存 <span class="wintitle"> 詳細狀態</span> 介面作為 <span class="filepath"> *.cfg</span> 可以在文本編輯器（如記事本）中開啟或分發給其他人的檔案 </p> </td> 
   <td colname="col2"> <p>以滑鼠右鍵按一下 <span class="uicontrol"> 詳細狀態</span> 標題和按一下 <span class="uicontrol"> 另存為</span>. </p> <p>注意：  <p>以滑鼠右鍵按一下 <span class="uicontrol"> 詳細狀態</span> 標題和按一下 <span class="uicontrol"> 儲存</span> to <i>伺服器名稱</i>/Status/在 <span class="wintitle"> 詳細狀態</span> 介面。 出現下列錯誤訊息： </p> <p>無法保存/Status/。 403禁止 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>要查看 <span class="uicontrol"> 每個日誌源的行數</span> 量度 </p> </td> 
   <td colname="col2"> <p>如果「詳細狀態」中需要報告「每個記錄來源的列」量度，則Data Workbench管理員應定義「記錄來源ID」，並在自訂設定檔的Log Processing.cfg中提供唯一名稱。 </p> </td> 
  </tr> 
 </tbody> 
</table>
