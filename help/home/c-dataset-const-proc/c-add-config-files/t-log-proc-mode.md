---
description: 設定檔案「記錄處理模式。cfg」可讓您暫停資料集中的資料處理、指定離線來源，或指定資料工作台伺服器儲存其狀態檔案的頻率。
solution: Analytics
title: 記錄處理模式。cfg
topic: Data workbench
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 記錄處理模式。cfg{#log-processing-mode-cfg}

設定檔案「記錄處理模式。cfg」可讓您暫停資料集中的資料處理、指定離線來源，或指定資料工作台伺服器儲存其狀態檔案的頻率。

對檔案進行變 [!DNL Log Processing Mode.cfg] 更（包括新增或移除來源）不會造成重新處理資料。

**若要編輯資料集描述檔的記錄處理模式。cfg檔案**

1. 在資料集設定檔中工作時，請開啟並 [!DNL Profile Manager] 按一下以 **[!UICONTROL Dataset]** 顯示其內容。

   >[!NOTE]
   >
   >如果文 [!DNL Log Processing Mode.cfg] 件未位於所需配置檔案的目錄中，則需要將此檔案從資料工作台伺服器電腦上的「基本」目錄複製到配置檔案的目錄中。

   如需開啟和使用的詳細資訊，請 [!DNL Profile Manager,] 參閱「資 *料工作台使用指南」*。

1. 按一下右鍵配置檔案名稱旁的複選標籤，然後按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 出現配置窗口。
1. 使用下表作為指南編輯配置檔案中的參數。

   >[!NOTE]
   >
   >檔案中的某些參 [!DNL Log Processing Mode.cfg] 數的名稱包括 [!DNL Fast Input] 或 [!DNL Fast Merge]。 [!DNL Fast Input]指的是資料集構建的日誌處理階段，約佔整個資料集處理時間的一半。 [!DNL Fast Merge] 是指只有在進行日誌處理之前才進行資料集構建的轉換階段。 [!DNL Fast Merge] 不會在修改檔案的重新轉換期間 [!DNL Transformation Dataset Configuration] 發生。 比 [!DNL Fast Input]如， [!DNL Fast Merge] 大約一半的資料集處理時間也由此產生。

   <table id="table_1BF356E21C0E4119A277F40CEC5D7A21"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 參數 </th> 
      <th colname="col2" class="entry"> 說明 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 雲端位元組 </td> 
      <td colname="col2"> <p>影響資料轉換效率的調整參數。 預設值為 128000000。 </p> <p> <p>注意： 您不應在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 快速輸入決策率 </td> 
      <td colname="col2"> <p>一種調整參數，它指定系統進入「快速輸入」模式(隨後是「快速合併」 <span class="wintitle"></span><span class="wintitle"></span>)而非即時處理資料的總和與未讀日誌位元組的比率。 </p> <p> 預設值為200，這表示當未讀取的日誌資料佔總資料的1/200時，系統從即時模式進入 <span class="wintitle"> Fast Input</span> mode。 較高的決策比使系統更容易進入 <span class="wintitle"> Fast Input</span> （快速輸入）模式，而較低的決策比則使系統較不可能進入 <span class="wintitle"> Fast Input（快速輸入）模式</span> 。 </p> <p> <p>注意：將參數設為0可讓系統完全無法進入「 <span class="wintitle"> 快速輸入</span> 」模式，即使在初始處理時亦然。 將參數設為1.1可讓系統在初始處理期間進入「 <span class="wintitle"> 快速輸入</span> 」，但不能在後續處理中。 Adobe不建議使用0到1.1之間的值。如需設定此參數的詳細資訊，請聯絡Adobe。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 快速輸入FIFO位元組 </td> 
      <td colname="col2"> <p>在資料處理期間平衡記憶體使用和系統效能的調整參數。 預設值為 120000000。 </p> <p> <p>注意： 您不應在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 快速合併緩衝區位元組 </td> 
      <td colname="col2"> <p>在資料處理期間平衡記憶體使用和系統效能的調整參數。 預設值為 128000000。 </p> <p> <p>注意： 您不應在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 離線來源 </td> 
      <td colname="col2"> <p>離線日誌源的掩碼。 </p> <p> <b> 若要指定離線來源</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> 以滑鼠右鍵按 <span class="uicontrol"> 一下「離線來源</span>」，然後按一下「 <span class="uicontrol"> 新增</span> &gt;來 <span class="uicontrol"> 源」</span>。 </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> 在新源的參數中，輸入日誌序列的掩碼。 對於檔案名為YYYYMMDD-<i>SENSORID</i>.vsl的感測器日誌源，掩碼為 <i>SENSORID.SENSORID</i> ，區分大小寫。 對於日誌檔案日誌源，掩碼是「掩碼模式」提取的 <span class="wintitle"> 字串</span>。 See <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> Log Files</a>. </li> 
      </ul> </p> <p> 從離線來源新增或移除來源時，不會重新處理資料集。 </p> <p> As Of time measurements is are maintenaned for the profile's online sources. 當離線來源再次連線時，該來源的傳入記錄檔處理會繼續。 </p> <p> 每當來源回線上時，您應從Offline Sources移除它。 如果您不這麼做，資料工作台伺服器會將來源視為線上來源，並更新「截止」時間，只要來源傳送資料。 如果來源再次離線，則「截止」時間測量將停止。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 已暫停 </td> 
      <td colname="col2"> 是非。 如果為true，則不會將新資料處理至資料集。 預設值為 false。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 即時延遲 </td> 
      <td colname="col2"> 資料工作台伺服器在處理資料至資料集的間隔間等候的時間（秒）。 當此值設為零時，系統會嘗試即時跟上傳入的資料。 預設值為零(0)，但您可以增加此值以降低CPU負載。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 即時FIFO位元組 </td> 
      <td colname="col2"> <p>用於儲存等待處理的資料到資料集的記憶體量（以位元組為單位）。 您可能需要根據您為「即時延遲」指定的秒數來變更此值。 預設值為 16000000。 </p> <p> <p>注意： 您不應在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 保存間隔（秒） </td> 
      <td colname="col2"> <p>資料工作台伺服器儲存其狀態檔案的頻率。 預設值為 3600。 </p> <p> <p>注意： 您不應在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   在資料工作台 [!DNL Log Processing Mode.cfg] 視窗中編輯檔案時，您可使用快速鍵進行基本編輯功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），並選取所有(Ctrl+a)。 此外，您也可以使用捷徑，將一個設定檔()的文字複製並貼到另 [!DNL .cfg]一個設定檔。

1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。
1. 在中， [!DNL Profile Manager]按一下右鍵列中檔案的複選標籤， [!DNL User] 然後按一下 **[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。
