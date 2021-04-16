---
description: 資料workbenchTransform.cfg檔案包含定義記錄檔來源、資料轉換和出口商的參數。
title: Transform.cfg 檔案
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 2%

---

# Transform.cfg 檔案{#the-transform-cfg-file}

資料workbenchTransform.cfg檔案包含定義記錄檔來源、資料轉換和出口商的參數。

您定義的轉換操作由感測器（[!DNL .vsl]檔案）收集或包含在文本檔案、XML檔案或ODBC相容資料庫中的原始資料，並將其輸出到現有欄位、覆蓋當前資料或新定義的欄位。

要配置轉換功能，請編輯要導出事件資料的配置檔案的「資料集」資料夾中的資料工作台[!DNL Transform.cfg]檔案。 通常，此配置檔案專用於轉換功能（即，除了資料工作台[!DNL Transform.cfg]檔案中定義的功能外，您不執行其他資料處理）。 請務必注意，除了資料工作台[!DNL Transform.cfg]檔案中指定的處理指令外，還會套用在[!DNL Log Processing Dataset Include]檔案中指定的任何繼承描述檔處理指令。

有關資料集包含檔案的資訊，請參見[ Dataset Include Files](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

如果要導出的資料由資料工作台伺服器集群處理，集群中的每個處理伺服器(DPU)都處理資料，但只有[!DNL profile.cfg]檔案中的第一個DPU（處理伺服器#0）將輸出資料寫入其本地檔案系統。

**若要編輯資料工作台Transform.cfg檔案**

1. 在要導出資料的配置檔案中工作時，開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示目錄的內容。
1. 以滑鼠右鍵按一下資料工作台[!DNL Transform.cfg]旁的核取標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 此檔案的複選標籤會出現在[!DNL User]列中。
1. 按一下右鍵新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL from the workbench]**。 此時將顯示資料工作台[!DNL Transform.cfg]窗口。
1. 使用下表作為指南編輯配置檔案中的參數：

<table id="table_91D9C4C1BE2E43158D9D06C6284EE3C7"> 
  <thead> 
    <tr> 
    <th colname="col1" class="entry"> 參數 </th> 
    <th colname="col2" class="entry"> 說明 </th> 
    </tr> 
  </thead>
  <tbody> 
    <tr> 
    <td colname="col1"> 結束時間 </td> 
    <td colname="col2"> <p>選填。篩選資料以包含時間戳記最多（但不包括）的記錄項目。 Adobe建議目前使用下列其中一種格式： 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 2013年1月1日美國東部夏令時間：HH:MM:SS </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，將2013年7月29日美國東部夏令時間00:00:00指定為<span class="wintitle">結束時間</span>包含2013年7月28日（美國東部夏令時間下午11:59:59）的資料。 </p> <p> 您必須指定時區。 如果未指定，時區不預設為GMT。 有關資料工作台伺服器支援的時區縮寫的清單，請參閱<a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">時區代碼</a>。 </p> <p> 感測器和日誌檔案源的使用開始／結束時間參數與此參數相關。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 出口商 </td> 
    <td colname="col2"> <p>導出器的子欄位指定輸出資料的處理和／或格式化方式。 您可以為一組日誌源定義多個出口商。 每個導出器類型都獨立建立輸出。 </p> <p> 有三類出口商： 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> 有關導出器類型的詳細資訊，請參閱<a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2">定義出口器</a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 雜湊閾值 </td> 
    <td colname="col2"> 選填。用於隨機行子採樣的採樣因子。 如果設為數字n，則每n個追蹤ID中只有一個會選取用於匯出，將匯出的列總數減少n倍。要導出所有行，應將「散列閾值」設定為1。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 記錄項目條件 </td> 
    <td colname="col2"> 選填。定義將日誌條目視為導出的規則。 有關<span class="wintitle">日誌條目條件</span>的詳細資訊，請參閱<a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">日誌處理配置檔案</a>。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 記錄來源 </td> 
    <td colname="col2"> <p>資料來源。 <span class="wintitle"> 日誌源 </span> 可以是 <span class="filepath"> .vsl文 </span> 件、日誌檔案或XML檔案或ODBC相容資料庫中的資料。有關<span class="wintitle">日誌源</span>的資訊，請參閱<a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md">日誌處理配置檔案</a>。 </p> <p> <span class="wintitle"> 轉換 </span> 期望所有來源資料在以字典排序的輸入檔案中按時間順序排列。如果不滿足此要求，則「截止」計算不正確，並且可以在輸出檔案關閉之後處理附加輸入資料。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 離線模式 </td> 
    <td colname="col2"> <p>選填。True 或 False. 如果為true，則<span class="wintitle">轉換</span>假定所有輸入檔案在開始處理資料時都存在。 當所有輸入資料都已被讀取時，<span class="wintitle">轉換</span>將關閉所有輸出檔案，而不等待接收其他資料。 預設值為 false。 </p> <p> <p>注意： 如果「離線模式</span>」設定為true，則「轉換</span>」預期在處理開始前所有源資料都會出現。 <span class="wintitle"><span class="wintitle">如果在輸出檔案關閉後收到其他資料，則在<span class="filepath"> VisualServer.log </span>檔案中會生成警告消息。 </span></span></p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 重新處理 </td> 
    <td colname="col2"> <p>選填。您可在此處輸入任何字元或字元組合。 更改此參數並將檔案保存到<span class="wintitle">轉換</span>機器會啟動資料重新處理。 </p> <p> 如需重新處理資料的詳細資訊，請參閱<a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">重新處理和重新轉換</a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 階段 </td> 
    <td colname="col2"> <p>選填。可用於<span class="wintitle">日誌處理資料集的處理階段名稱包括除資料工作台<span class="filepath"> Transform.cfg </span>檔案外還執行的</span>檔案。 處理階段提供了對<span class="wintitle">日誌處理資料集包含</span>檔案中定義的轉換排序的方法。 如果您已在多個<span class="wintitle">日誌處理資料集包含</span>檔案中定義了一個或多個轉換，並且希望在導出過程中在特定點執行特定轉換，則此參數非常有用。 </p> <p> 在此處列出階段的順序決定了在資料導出期間執行<span class="wintitle">日誌處理資料集包含</span>檔案中轉換的順序。 <span class="wintitle"> 預處 </span> 理和 <span class="wintitle"> 後處 </span> 理是內置的階段； <span class="wintitle"> 預處 </span> 理總是第一個階段， <span class="wintitle"> 後處 </span> 理總是最後一個階段。預設情況下，有一個名為<span class="wintitle"> Default </span>的命名階段。 </p> <p> <b>若要新增處理階段</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> 在「資料工作台<span class="filepath"> Transform.cfg </span>」視窗中，以滑鼠右鍵按一下「<span class="uicontrol">階段</span>」，然後按一下「新增</span> &gt; <span class="uicontrol">階段</span>」。<span class="uicontrol"> </span></li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> 輸入新階段的名稱。 </li> 
      </ul> <p> <b>刪除現有處理階段</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> 按一下右鍵要刪除的階段所對應的編號，然後按一下<span class="uicontrol">刪除</span><i>&lt;<span class="uicontrol"> #stage_number </span>&gt;</i>。 </li> 
      </ul> <p> <p>注意： 在<span class="wintitle">記錄處理資料集包含</span>檔案中指定「舞台」時，舞台名稱必須與您在此處輸入的名稱完全相符。 如需資料集包含檔案的詳細資訊，請參閱<a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md">資料集包含檔案</a>。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 開始時間 </td> 
    <td colname="col2"> <p>選填。篩選資料，以包含目前或之後具有時間戳記的記錄項目。 Adobe建議目前使用下列其中一種格式： </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 2013年1月1日美國東部夏令時間 </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> <p> 例如，指定「2013年7月29日美國東部夏令時間」為「開始時間」時，會包含從2013年7月29日美國東部夏令時間12:00:00開始的資料。 </p> <p> 您必須指定時區。 如果未指定，時區不預設為GMT。 有關資料工作台伺服器支援的時區縮寫的清單，請參閱<a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">時區代碼</a>。 </p> <p> <p>注意： 感測器和日誌檔案源的使用開始／結束時間參數與此參數相關。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 轉換 </td> 
    <td colname="col2"> <p>選填。定義要應用於資料的轉換。 有關可用轉換類型的資訊，請參閱<a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md">資料轉換</a>。 </p> <p> <p>注意： 在資料工作台<span class="filepath"> Transform.cfg </span>檔案中定義下列轉換類型時，無法運作： </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> Sessionize </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>如果在輸出檔案關閉後收到其他資料（請參見上表中的[!DNL Log Sources]和[!DNL Offline Mode]），則[!DNL Transform]將建立具有附加資料的新輸出檔案。 新輸出檔案的名稱是從原始輸出檔案的名稱生成的，並在副檔名前面添加一個括弧內的版本號。 例如，如果原始輸出檔案為[!DNL 20070701-ABC.vsl]，則此檔案的後續版本將命名為[!DNL 20070701-ABC(1).vsl]、[!DNL 20070701-ABC(2).vsl]等。 請注意，將版本化檔案輸入至資料工作台伺服器可能會導致處理錯誤。
>
>
>Adobe建議避免建立版本化輸出檔案，方法是確保所有源資料都按時間順序排列在詞典排序的輸入檔案中，如果[!DNL Offline Mode]設定為true，則在處理開始前所有源資料都存在。 有關詳細資訊，請參見上表中的[!DNL Log Sources]和[!DNL Offline Mode]條目。

1. 按一下右鍵&#x200B;**[!UICONTROL Transformations]**&#x200B;並按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**&#x200B;添加轉換。 完成轉換欄位。

   有關可用於轉換功能的轉換的說明和示例，請參見[資料轉換](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 若要讓本機所做的變更生效，請在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中資料工作台[!DNL Transform.cfg]的核取標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL profile name]**，其中描述檔名稱是您匯出資料的描述檔名稱。 重新處理資料是在設定檔同步後開始。

   >[!NOTE]
   >
   >如需重新處理資料以進行匯出的詳細資訊，請參閱[重新處理和重新轉換](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
