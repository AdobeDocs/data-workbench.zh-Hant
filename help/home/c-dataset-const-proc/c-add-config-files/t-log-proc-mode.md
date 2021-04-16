---
description: 設定檔案「記錄處理模式。cfg」可讓您暫停資料集中的資料處理、指定離線來源，或指定資料工作台伺服器儲存其狀態檔案的頻率。
title: Log Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

設定檔案「記錄處理模式。cfg」可讓您暫停資料集中的資料處理、指定離線來源，或指定資料工作台伺服器儲存其狀態檔案的頻率。

對[!DNL Log Processing Mode.cfg]檔案進行變更（包括新增或移除來源）不會造成重新處理資料。

**若要編輯資料集描述檔的記錄處理模式。cfg檔案**

1. 在資料集設定檔中工作時，開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。

   >[!NOTE]
   >
   >如果[!DNL Log Processing Mode.cfg]檔案未位於所需配置檔案的目錄中，則需要將此檔案從資料工作台伺服器電腦上的「基本」目錄複製到配置檔案的目錄中。

   有關開啟和使用[!DNL Profile Manager,]的資訊，請參閱&#x200B;*Data Workbench使用手冊*。

1. 按一下右鍵配置檔案名稱旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。
1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現配置窗口。
1. 使用下表作為指南編輯配置檔案中的參數。

   >[!NOTE]
   >
   >[!DNL Log Processing Mode.cfg]檔案中的某些參數的名稱包括[!DNL Fast Input]或[!DNL Fast Merge]。 [!DNL Fast Input]指的是資料集構建的日誌處理階段，約佔整個資料集處理時間的一半。[!DNL Fast Merge] 是指只有在進行日誌處理之前才進行資料集構建的轉換階段。[!DNL Fast Merge] 不會在修改檔案的重新轉換期間 [!DNL Transformation Dataset Configuration] 發生。與[!DNL Fast Input]一樣，[!DNL Fast Merge]也貢獻了大約一半的資料集處理時間。

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
      <td colname="col2"> <p>一種調整參數，它指定系統進入<span class="wintitle">快速輸入</span>模式（隨後是<span class="wintitle">快速合併</span>）而不是即時處理資料的總和與未讀日誌位元組的比率。 </p> <p> 預設值為200，這表示當未讀日誌資料佔總資料的1/200時，系統從即時模式進入「快速輸入」模式。 <span class="wintitle"></span>較高的決策比使得系統更容易進入<span class="wintitle">快速輸入</span>模式，而較低的決策比使系統更不可能進入<span class="wintitle">快速輸入</span>模式。 </p> <p> <p>注意：將參數設定為0可使系統完全無法進入「快速輸入」模式，即使初始處理也是如此。 <span class="wintitle"></span>將參數設定為1.1可使系統在初始處理期間進入「快速輸入」，但不能進入後續處理。 <span class="wintitle"></span>Adobe不建議使用0到1.1之間的值。如需設定此參數的詳細資訊，請連絡Adobe。 </p> </p> </td> 
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
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> 按一下右鍵<span class="uicontrol"> Offline Sources</span> ，然後按一下<span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> Source</span>。 </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> 在新源的參數中，輸入日誌序列的掩碼。 對於檔案名為YYYYMMDD-<i>SENSORID</i>.vsl的感測器日誌源，掩碼為<i>SENSORID.SENSORID</i>區分大小寫。 對於日誌檔案日誌源，掩碼是<span class="wintitle">掩碼模式</span>提取的字串。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e">日誌檔案</a>。 </li> 
      </ul> </p> <p> 從離線來源新增或移除來源時，不會重新處理資料集。 </p> <p> As Of time measurements is are maintenaned for the profile's online sources. 當離線來源再次連線時，該來源的傳入記錄檔處理會繼續。 </p> <p> 每當來源重新連線時，您應將其從Offline Sources移除。 如果您不這麼做，資料工作台伺服器會將來源視為線上來源，並更新「截止」時間，只要來源傳送資料。 如果來源再次離線，則「截止」時間測量將停止。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 已暫停 </td> 
      <td colname="col2"> True 或 False. 如果為true，則不會將新資料處理至資料集。 預設值為 false。 </td> 
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

   在資料工作台視窗中編輯[!DNL Log Processing Mode.cfg]檔案時，您可使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），然後選取所有(Ctrl+a)。 此外，您還可以使用捷徑，將一個設定檔案([!DNL .cfg])的文字複製並貼到另一個設定檔。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**。

   >[!NOTE]
   >
   >請勿將修改過的配置檔案保存到Adobe提供的任何內部配置檔案中，因為安裝這些配置檔案的更新時將覆蓋您所做的更改。
