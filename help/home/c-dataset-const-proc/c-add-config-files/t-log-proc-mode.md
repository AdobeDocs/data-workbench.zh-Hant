---
description: 設定檔案Log Processing Mode.cfg可讓您暫停將資料處理至資料集、指定離線來源，或指定Data Workbench伺服器儲存其狀態檔案的頻率。
title: Log Processing Mode.cfg
uuid: 1f1e5d8b-80e7-4423-bb03-56e706a1b7b4
exl-id: e252b815-e691-490d-9ac9-88bb1fd2c64d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 3%

---

# Log Processing Mode.cfg{#log-processing-mode-cfg}

設定檔案Log Processing Mode.cfg可讓您暫停將資料處理至資料集、指定離線來源，或指定Data Workbench伺服器儲存其狀態檔案的頻率。

對[!DNL Log Processing Mode.cfg]檔案進行變更（包括新增或移除來源）不會導致重新處理資料。

**編輯資料集設定檔的Log Processing Mode.cfg檔案的方式**

1. 在資料集設定檔中工作時，請開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。

   >[!NOTE]
   >
   >如果[!DNL Log Processing Mode.cfg]檔案未位於所需設定檔的目錄中，則您需要將此檔案從Data Workbench伺服器電腦上的Base目錄複製到設定檔的目錄中。

   有關開啟和使用[!DNL Profile Manager,]的資訊，請參閱&#x200B;*Data Workbench使用手冊*。

1. 按一下右鍵配置檔案名稱旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。
1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此時將出現配置窗口。
1. 使用下表作為指南編輯配置檔案中的參數。

   >[!NOTE]
   >
   >[!DNL Log Processing Mode.cfg]檔案中的某些參數的名稱包括[!DNL Fast Input]或[!DNL Fast Merge]。 [!DNL Fast Input]是指資料集建構的記錄處理階段，約佔資料集處理時間的一半。[!DNL Fast Merge] 是指只有在進行記錄處理之前，才會進行資料集建構的轉換階段。[!DNL Fast Merge] 在因修改檔案而導致的重新轉換期間不會 [!DNL Transformation Dataset Configuration] 發生。與[!DNL Fast Input]類似， [!DNL Fast Merge]也大約佔資料集處理時間的一半。

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
      <td colname="col2"> <p>影響資料轉換效率的調整參數。 預設值為 128000000。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 快速輸入決策比 </td> 
      <td colname="col2"> <p>一個調整參數，它指定系統進入<span class="wintitle">快速輸入</span>模式（隨後進入<span class="wintitle">快速合併</span>）時的總日誌位元組與未讀日誌位元組的比率，而不是即時處理資料。 </p> <p> 預設值為200，表示當未讀日誌資料為總資料的1/200時，系統從即時模式進入「快速輸入」模式。 <span class="wintitle"></span>較高的決策比使系統更容易進入<span class="wintitle">快速輸入</span>模式，而較低的決策比使系統更不可能進入<span class="wintitle">快速輸入</span>模式。 </p> <p> <p>注意：將參數設定為0，即使進行初始處理，系統也完全不會進入「快速輸入」模式。 <span class="wintitle"></span>將參數設定為1.1可讓系統在初始處理期間輸入<span class="wintitle">快速輸入</span>，但不用於後續處理。 Adobe不建議使用介於0和1.1之間的值。如需設定此參數的詳細資訊，請聯絡Adobe。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 快速輸入FIFO位元組 </td> 
      <td colname="col2"> <p>在資料處理期間平衡記憶體使用和系統效能的調整參數。 預設值為 120000000。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 快速合併緩衝位元組 </td> 
      <td colname="col2"> <p>在資料處理期間平衡記憶體使用和系統效能的調整參數。 預設值為 128000000。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 離線來源 </td> 
      <td colname="col2"> <p>離線日誌源的掩碼。 </p> <p> <b> 指定離線源</b> 
      <ul id="ul_569B90E9A85246F88906FA5444F8A93E"> 
       <li id="li_3EF182CEF4A44106B5267175EC62B9AB"> 按一下右鍵「<span class="uicontrol">離線源</span>」，然後按一下「<span class="uicontrol">新增</span> &gt; <span class="uicontrol">源</span>」。 </li> 
       <li id="li_E8FBA212F4784B1A830745A90BB3AF90"> 在新源的參數中，輸入日誌序列的掩碼。 對於檔案名為YYYYMMDD-<i>SENSORID</i>.vsl的感測器日誌源，掩碼為<i>SENSORID.SENSORID</i>，區分大小寫。 對於日誌檔案日誌源，掩碼是由<span class="wintitle">掩碼模式</span>提取的字串。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e">日誌檔案</a>。 </li> 
      </ul> </p> <p> 從離線來源新增或移除來源時，不會重新處理資料集。 </p> <p> 處理設定檔的線上來源時，會維護「截止時間」測量。 離線源再次聯機時，該源的傳入日誌檔案的處理將繼續。 </p> <p> 每當來源重新上線時，您應將其從離線來源中移除。 若您未這麼做，Data Workbench伺服器會將來源視為線上來源，只要來源傳送資料，就會更新「截止」時間。 如果源再次離線，則「截止時間」測量將停止。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 已暫停 </td> 
      <td colname="col2"> True 或 False. 若為true，系統不會將新資料處理至資料集。 預設值為 false。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 即時延遲 </td> 
      <td colname="col2"> Data Workbench伺服器在處理資料至資料集的間隔之間等候的秒數。 當此值設為零時，系統會嘗試即時追蹤傳入的資料。 預設值為零(0)，但您可以增加此值以減少CPU負載。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 即時FIFO位元組 </td> 
      <td colname="col2"> <p>儲存等待處理的資料至資料集的記憶體量（以位元組為單位）。 您可能需要根據您為「即時延遲」指定的秒數來變更此值。 預設值為 16000000。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 保存間隔（秒） </td> 
      <td colname="col2"> <p>Data Workbench伺服器儲存其狀態檔案的頻率。 預設值為 3600。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   在Data Workbench視窗中編輯[!DNL Log Processing Mode.cfg]檔案時，您可以使用快速鍵來編輯基本的編輯功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、還原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取全部(Ctrl+a)。 此外，還可以使用快捷方式將文本從一個配置檔案([!DNL .cfg])複製並貼到另一個配置檔案。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中檔案的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL datasetprofile name]**。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。
