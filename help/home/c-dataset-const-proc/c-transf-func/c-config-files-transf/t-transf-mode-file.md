---
description: 設定檔Transform Mode.cfg可讓您暫停資料集中的資料處理、指定離線來源，或指定執行轉換功能的資料工作台伺服器儲存其狀態檔案的頻率。
solution: Analytics
title: 轉換模式。cfg檔案
topic: Data workbench
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 轉換模式。cfg檔案{#the-transform-mode-cfg-file}

設定檔Transform Mode.cfg可讓您暫停資料集中的資料處理、指定離線來源，或指定執行轉換功能的資料工作台伺服器儲存其狀態檔案的頻率。

對檔案進行變 [!DNL Transform Mode.cfg] 更（包括新增或移除來源）不會造成重新處理資料。

**若要編輯資料集描述檔的轉換模式。cfg檔案**

1. 在要導出其資料的配置檔案中工作時，開啟 [!DNL Profile Manager] 並按一下 **[!UICONTROL Dataset]** 以顯示目錄的內容。
1. 按一下右鍵旁邊的複選標 [!DNL Transform Mode.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 出現 [!DNL Transform Mode.cfg] 窗口。
1. 使用下表作為指南編輯配置檔案中的參數：

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 參數 </th> 
    <th colname="col2" class="entry"> 說明 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> 離線來源 </td> 
    <td colname="col2"> <p>離線日誌源的掩碼。 </p> <p> 要指定離線源，請執行以下操作： </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> 以滑鼠右鍵按 <span class="uicontrol"> 一下「離線來源</span> 」，然後按 <span class="uicontrol"> 一下「新增</span> &gt;來 <span class="uicontrol"> 源」</span>。 </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> 在新源的參數中，輸入日誌序列的掩碼。 對於檔案名為 <span class="filepath"> YYYYMMDD-SENSORID.vsl格式的感測器日誌源</span>，掩碼為 <i>SENSORID.SENSORID</i> ，區分大小寫。 對於日誌檔案日誌源，掩碼是由「掩碼模式」提取的 <span class="wintitle"> 字串</span> (請參見 <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> 「日誌檔案」</a>)。 </li> 
    </ul> <p> 從離線來源新增或移除來 <span class="wintitle"> 源時</span> ，不會重新處理資料集。 </p> <p> As Of time measurements is are maintenaned for the profile's online sources. 當離線來源再次連線時，該來源的傳入記錄檔處理會繼續。 </p> <p> <p>注意：每當來源回線上時，您應將其從 <span class="wintitle"> Offline Sources移除</span>。 如果您不這麼做，資料工作台伺服器會將來源視為線上來源，並更新「截止」時間，只要來源傳送資料。 如果來源再次離線，則「截止」時間測量將停止。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 已暫停 </td> 
    <td colname="col2"> 是非。 如果為true，則不會將新資料處理至資料集。 預設值為 false。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 保存間隔（秒） </td> 
    <td colname="col2"> <p>執行轉換功能的資料工作台伺服器的頻率會儲存其狀態檔案。 預設值為 3600。 </p> <p> <p>注意： 您不應在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   在資料工作台 [!DNL Transform Mode.cfg] 視窗中編輯檔案時，您可使用快速鍵進行基本編輯功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），並選取所有(Ctrl+a)。 此外，您也可以使用捷徑，將一個設定檔()的文字複製並貼到另 [!DNL .cfg]一個設定檔。

1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。
1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下資料工作台的核取標籤，然後按一下 [!DNL Transform Mode.cfg] > [!DNL User]**[!UICONTROL Save to]****[!UICONTROL profile name]**，其中描述檔名稱是您要匯出資料的描述檔名稱。 重新處理資料是在設定檔同步後開始。

   如需重新處理資料以進行匯出的詳細資訊，請參 [閱重新處理和轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
