---
description: 資料workbenchTransform.cfg檔案包含定義記錄檔來源、資料轉換和出口商的參數。
solution: Analytics
title: Transform.cfg檔案
topic: Data workbench
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Transform.cfg檔案{#the-transform-cfg-file}

資料workbenchTransform.cfg檔案包含定義記錄檔來源、資料轉換和出口商的參數。

您定義的轉換操作由感測器（檔案）收集或包含在文本檔案、XML檔案或ODBC相容資料庫中的原始資料，並將它們輸出到現有欄位、覆寫當前資料或新定義的欄位。 [!DNL .vsl]

若要設定轉換功能，請編輯您要匯出事 [!DNL Transform.cfg] 件資料之描述檔的「資料集」資料夾中的資料工作台檔案。 通常，此配置檔案專用於轉換功能(即，除了資料工作台檔案中定義的資料之外，您不執行其他資料 [!DNL Transform.cfg] 處理)。 請務必注意，除了資料工作台檔案中指定的指令外， [!DNL Log Processing Dataset Include] 檔案中為任何繼承的描述檔指定的任何處理指令都會 [!DNL Transform.cfg] 套用。

如需資料集包含檔案的詳細資訊，請參 [閱資料集包含檔案](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

如果要導出的資料由資料工作台伺服器集群處理，則集群中的每個處理伺服器(DPU)都處理資料，但只有第一個DPU（檔案中的處理伺服器#0）將將輸出資料寫入其本地檔案系統。 [!DNL profile.cfg]

**若要編輯資料工作台Transform.cfg檔案**

1. 在要導出資料的配置檔案中工作時，開啟並單 [!DNL Profile Manager] 擊以 **[!UICONTROL Dataset]** 顯示目錄的內容。
1. 以滑鼠右鍵按一下資料工作台旁的核取標 [!DNL Transform.cfg]記，然後按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL from the workbench]**。 此時將顯示數 [!DNL Transform.cfg] 據工作台窗口。
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
    <td colname="col2"> <p>選填。篩選資料以包含時間戳記最多（但不包括）的記錄項目。 Adobe建議您目前使用下列其中一種格式： 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 2013年1月1日美國東部夏令時間：HH:MM:SS </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定「2013年7月29日美國東部夏令時間00:00:00」作為「結束時間」, <span class="wintitle"></span> 包括截至2013年7月28日（美國東部夏令時間下午11:59:59）的資料。 </p> <p> 您必須指定時區。 如果未指定，時區不預設為GMT。 如需資料工作台伺服器支援的時區縮寫清單，請參閱時區 <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 代碼 </a>。 </p> <p> 感測器和日誌檔案源的使用開始／結束時間參數與此參數相關。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 出口商 </td> 
    <td colname="col2"> <p>導出器的子欄位指定輸出資料的處理和／或格式化方式。 您可以為一組日誌源定義多個出口商。 每個導出器類型都獨立建立輸出。 </p> <p> 有三類出口商： 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimitedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> 有關導出器類型的詳細資訊，請參 <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> 閱定義出口商 </a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 雜湊閾值 </td> 
    <td colname="col2"> 選填。用於隨機行子採樣的採樣因子。 如果設為數字n，則每n個追蹤ID中只有一個會選取用於匯出，將匯出的列總數減少n倍。要導出所有行，應將「散列閾值」設定為1。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 日誌條目條件 </td> 
    <td colname="col2"> 選填。定義將日誌條目視為導出的規則。 有關「日誌條目條件」 <span class="wintitle"> 的詳細信 </span>息，請 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 參閱日誌處理配置檔案 </a>。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 記錄來源 </td> 
    <td colname="col2"> <p>資料來源。 <span class="wintitle"> 日誌源 </span> 可以是。vsl <span class="filepath"> 文 </span> 件、日誌檔案或XML檔案，也可以是ODBC相容資料庫的資料。 有關日誌源的 <span class="wintitle"> 資訊，請 </span>參閱日 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 志處理配置檔案 </a>。 </p> <p> <span class="wintitle"> 轉換 </span> 期望所有來源資料在以字典排序的輸入檔案中按時間順序排列。 如果不滿足此要求，則「截止」計算不正確，並且可以在輸出檔案關閉之後處理附加輸入資料。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 離線模式 </td> 
    <td colname="col2"> <p>選填。是非。 如果為true, <span class="wintitle"> 則Transform </span> 會假設所有輸入檔案在開始處理資料時都存在。 當所有輸入資料都已被讀取時，轉換 <span class="wintitle"> 會 </span> 關閉所有輸出檔案，而不等待接收其他資料。 預設值為 false。 </p> <p> <p>注意： 如果 <span class="wintitle"> 離線模 </span> 式設定為true，則 <span class="wintitle"> Transform </span> 會在處理開始之前預期所有源資料都存在。 如果在輸出檔案關閉後收到 <span class="filepath"> 其他資料，VisualServer.log </span> 檔案中將生成警告消息。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 重新處理 </td> 
    <td colname="col2"> <p>選填。您可在此處輸入任何字元或字元組合。 更改此參數並將檔案保存到「轉換」機 <span class="wintitle"> 器 </span> 會啟動資料重新處理。 </p> <p> 如需重新處理資料的詳細資訊，請參閱重新 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 處理和重新轉換 </a>。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 階段 </td> 
    <td colname="col2"> <p>選填。可用於記錄處理資料集的處理階段名稱，包 <span class="wintitle"> 括除了資料工作台 </span> Transform.cfg檔案外，還執行的 <span class="filepath"></span> 檔案。 處理階段提供了一種對「日誌處理資料集包含」檔案中定 <span class="wintitle"> 義的轉換排序的 </span> 方法。 如果您已在多個記錄處理資料集包含檔案中定義一或多個轉換，且您希望在匯出程式期間在特定點執行特定轉換， <span class="wintitle"></span> 此參數會非常有用。 </p> <p> 在此處列出階段的順序決定了在資料導出期間執行「日誌處理資料集包含」文 <span class="wintitle"></span> 件轉換的順序。 <span class="wintitle"> 預處理 </span> 和 <span class="wintitle"> 後處理 </span> 是內置的階段；預 <span class="wintitle"> 處理 </span> 總是第一個階段，後處理 <span class="wintitle"></span> 總是最後一個階段。 依預設，有一個名為「預設」的命 <span class="wintitle"> 名階段 </span>。 </p> <p> <b>若要新增處理階段</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> 在資料工作台的 <span class="filepath"> Transform.cfg </span> 視窗中，以滑鼠右鍵按一 <span class="uicontrol"> 下「階段」，然後按一下「新增 </span>&gt; <span class="uicontrol"></span><span class="uicontrol"></span>階段」。 </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> 輸入新階段的名稱。 </li> 
      </ul> <p> <b>刪除現有處理階段</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> 按一下右鍵要刪除的階段所對應的編號，然後按一下 <span class="uicontrol"> 刪 </span><i>除 <span class="uicontrol"> &lt; #stage_number </span>&gt;</i>。 </li> 
      </ul> <p> <p>注意： 當您在「記錄處理資料集包 <span class="wintitle"> 含」檔案中指定「舞台」 </span> 時，舞台的名稱必須完全符合您在此處輸入的名稱。 如需資料集包含檔案的詳細資訊，請參閱資料集 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 包含檔案 </a>。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 開始時間 </td> 
    <td colname="col2"> <p>選填。篩選資料，以包含目前或之後具有時間戳記的記錄項目。 Adobe建議您目前使用下列其中一種格式： </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 2013年1月1日美國東部夏令時間 </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> <p> 例如，指定「2013年7月29日美國東部夏令時間」為「開始時間」時，會包含從2013年7月29日美國東部夏令時間12:00:00開始的資料。 </p> <p> 您必須指定時區。 如果未指定，時區不預設為GMT。 如需資料工作台伺服器支援的時區縮寫清單，請參閱時區 <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 代碼 </a>。 </p> <p> <p>注意： 感測器和日誌檔案源的使用開始／結束時間參數與此參數相關。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 轉換 </td> 
    <td colname="col2"> <p>選填。定義要應用於資料的轉換。 有關可用轉換類型的資訊，請參 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 閱資料轉換 </a>。 </p> <p> <p>注意： 在資料工作台 <span class="filepath"> Transform.cfg檔案中定義時，下列轉換類型無 </span> 法運作： </p> </p> 
      <ul id="ul_B091DFBD1C33471BBC01AEC7E92FC8CC"> 
       <li id="li_660EBECFC407488199CCCC886326806D"> AppendURI </li> 
       <li id="li_56BCEBE4A2D044AE87F5B747C6501817"> CrossRows </li> 
       <li id="li_B23B4E81B37942DCA55FEC1A6239C5FA"> ODBCLookup </li> 
       <li id="li_EF0AFF13C40D4AB49EAB4EF1691F8FA4"> 作業化 </li> 
      </ul> </td> 
    </tr> 
  </tbody> 
  </table>

>[!NOTE]
>
>如果在輸出檔案關閉後收到其它資料(請參見 [!DNL Log Sources] 上 [!DNL Offline Mode] 表和), [!DNL Transform] 則使用附加資料建立新的輸出檔案。 新輸出檔案的名稱是從原始輸出檔案的名稱生成的，並在副檔名前面添加一個括弧內的版本號。 例如，如果原始輸出檔案 [!DNL 20070701-ABC.vsl]是，則此檔案的後續版本將命 [!DNL 20070701-ABC(1).vsl]名 [!DNL 20070701-ABC(2).vsl]，依此類推。 請注意，將版本化檔案輸入至資料工作台伺服器可能會導致處理錯誤。
>
>
>Adobe建議避免建立版本化輸出檔案，方法是確定所有來源資料都依時間順序排列在以字典排序的輸入檔案中，若設為 [!DNL Offline Mode] true，則在處理開始前，所有來源資料都會出現。 有關詳細資訊，請參 [!DNL Log Sources] 閱上 [!DNL Offline Mode] 表中的和條目。

1. 以滑鼠右鍵按一下並按 **[!UICONTROL Transformations]** 下 **[!UICONTROL Add new]** >以新增轉 **[!UICONTROL Transformation type]**&#x200B;換。 完成轉換欄位。

   有關可 [](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) 與轉換功能一起使用的轉換的說明和示例，請參閱資料轉換。

1. 在視窗頂 **[!UICONTROL (modified)]** 端按一下滑鼠右鍵，然後按一下 **[!UICONTROL Save]**。
1. 若要讓本機所做的變更生效，請在欄中 [!DNL Profile Manager]，以滑鼠右鍵按一下資料工作台的核取標籤，然後按一下 [!DNL Transform.cfg] > [!DNL User]**[!UICONTROL Save to]****[!UICONTROL profile name]**，其中描述檔名稱是您要匯出資料的描述檔名稱。 重新處理資料是在設定檔同步後開始。

   >[!NOTE]
   >
   >如需重新處理資料以進行匯出的詳細資訊，請參 [閱重新處理和轉換](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
