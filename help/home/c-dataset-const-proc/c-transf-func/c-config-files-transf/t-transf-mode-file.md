---
description: 設定檔Transform Mode.cfg可讓您暫停資料集中的資料處理、指定離線來源，或指定執行轉換功能的資料工作台伺服器儲存其狀態檔案的頻率。
title: Transform Mode.cfg 檔案
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 4%

---

# Transform Mode.cfg 檔案{#the-transform-mode-cfg-file}

設定檔Transform Mode.cfg可讓您暫停資料集中的資料處理、指定離線來源，或指定執行轉換功能的資料工作台伺服器儲存其狀態檔案的頻率。

對[!DNL Transform Mode.cfg]檔案進行變更（包括新增或移除來源）不會造成重新處理資料。

**若要編輯資料集描述檔的轉換模式。cfg檔案**

1. 在要導出其資料的配置檔案中工作時，開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示目錄的內容。
1. 按一下右鍵[!DNL Transform Mode.cfg]旁邊的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。
1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 出現[!DNL Transform Mode.cfg]窗口。
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
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> 按一下右鍵<span class="uicontrol"> Offline Sources</span> ，然後按一下<span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> Source</span>。 </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> 在新源的參數中，輸入日誌序列的掩碼。 對於檔案名為<span class="filepath"> YYYYMMDD-SENSORID.vsl</span>的感測器日誌源，掩碼為<i>SENSORID.SENSORID</i>，區分大小寫。 對於日誌檔案日誌源，掩碼是由<span class="wintitle">掩碼模式</span>提取的字串（請參見<a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e">日誌檔案</a>）。 </li> 
    </ul> <p> 從<span class="wintitle">離線來源</span>新增或移除來源時，不會造成資料集重新處理。 </p> <p> As Of time measurements is are maintenaned for the profile's online sources. 當離線來源再次連線時，該來源的傳入記錄檔處理會繼續。 </p> <p> <p>注意：每當來源重新連線時，您應從<span class="wintitle"> Offline Sources</span>移除它。 如果您不這麼做，資料工作台伺服器會將來源視為線上來源，並更新「截止」時間，只要來源傳送資料。 如果來源再次離線，則「截止」時間測量將停止。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 已暫停 </td> 
    <td colname="col2"> True 或 False. 如果為true，則不會將新資料處理至資料集。 預設值為 false。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 保存間隔（秒） </td> 
    <td colname="col2"> <p>執行轉換功能的資料工作台伺服器的頻率會儲存其狀態檔案。 預設值為 3600。 </p> <p> <p>注意： 您不應在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   在資料工作台視窗中編輯[!DNL Transform Mode.cfg]檔案時，您可使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），然後選取所有(Ctrl+a)。 此外，您還可以使用捷徑，將一個設定檔案([!DNL .cfg])的文字複製並貼到另一個設定檔。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 要使本地更改生效，請在[!DNL Profile Manager]中按一下右鍵[!DNL User]列中資料工作台[!DNL Transform Mode.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]** ，其中配置檔案名稱是要導出資料的配置檔案的名稱。 重新處理資料是在設定檔同步後開始。

   如需重新處理資料以進行匯出的詳細資訊，請參閱[重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
