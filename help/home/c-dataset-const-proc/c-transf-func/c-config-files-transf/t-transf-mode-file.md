---
description: 設定檔案Transform Mode.cfg可讓您將資料處理暫停為資料集、指定離線來源，或指定執行轉換功能的Data Workbench伺服器儲存其狀態檔案的頻率。
title: Transform Mode.cfg 檔案
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# Transform Mode.cfg 檔案{#the-transform-mode-cfg-file}

{{eol}}

設定檔案Transform Mode.cfg可讓您將資料處理暫停為資料集、指定離線來源，或指定執行轉換功能的Data Workbench伺服器儲存其狀態檔案的頻率。

變更 [!DNL Transform Mode.cfg] 檔案（包括新增或移除來源）不會造成資料的重新處理。

**編輯資料集設定檔的Transform Mode.cfg檔案的方式**

1. 在要匯出其資料的設定檔中工作時，請開啟 [!DNL Profile Manager] 按一下 **[!UICONTROL Dataset]** 顯示目錄的內容。
1. 以滑鼠右鍵按一下旁的核取記號 [!DNL Transform Mode.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. 此 [!DNL Transform Mode.cfg] 的上界。
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
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> 按一下右鍵 <span class="uicontrol"> 離線來源</span> 按一下 <span class="uicontrol"> 新增</span> &gt; <span class="uicontrol"> 來源</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> 在新源的參數中，輸入日誌序列的掩碼。 對於檔案名為格式的感測器日誌源 <span class="filepath"> YYYYMMDD-SENSORID.vsl</span>，蒙版是 <i>SENSORID.SENSORID</i> 區分大小寫。 對於記錄檔記錄來源，遮罩是擷取的字串 <span class="wintitle"> 遮色片圖樣</span> (請參閱 <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> 記錄檔</a>)。 </li> 
    </ul> <p> 添加或刪除源 <span class="wintitle"> 離線來源</span> 不會重新處理資料集。 </p> <p> 處理設定檔的線上來源時，會維護「截止時間」測量。 離線源再次聯機時，該源的傳入日誌檔案的處理將繼續。 </p> <p> <p>注意：每當源重新聯機時，您應將其從 <span class="wintitle"> 離線來源</span>. 若您未這麼做，Data Workbench伺服器會將來源視為線上來源，只要來源傳送資料，就會更新「截止」時間。 如果源再次離線，則「截止時間」測量將停止。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 已暫停 </td> 
    <td colname="col2"> True或False。 若為true，系統不會將新資料處理至資料集。 預設值為 false。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 保存間隔（秒） </td> 
    <td colname="col2"> <p>執行轉換功能的Data Workbench伺服器會儲存其狀態檔案的頻率。 預設值為 3600。 </p> <p> <p>注意：若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   編輯 [!DNL Transform Mode.cfg] 檔案時，您可以使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、還原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取全部(Ctrl+a)。 此外，您可以使用捷徑來複製和貼上來自一個設定檔案的文字( [!DNL .cfg])到其他。

1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.
1. 若要讓本機所做的變更生效，請在 [!DNL Profile Manager]，請以滑鼠右鍵按一下data workbench的勾選記號 [!DNL Transform Mode.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > **[!UICONTROL profile name]**，其中profile name是要匯出資料之設定檔的名稱。 同步設定檔後，就會開始重新處理資料。

   如需重新處理資料以進行匯出的詳細資訊，請參閱 [重新處理和重新轉換](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
