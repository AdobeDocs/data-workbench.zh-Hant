---
description: data workbenchTransform.cfg檔案包含定義記錄來源、資料轉換和匯出工具的參數。
title: Transform.cfg 檔案
uuid: eab5bb70-6de7-4f08-85db-a6cb00abd3ed
exl-id: e84f2536-cb22-4c47-a7a8-270b3c37ece6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 2%

---

# Transform.cfg 檔案{#the-transform-cfg-file}

{{eol}}

data workbenchTransform.cfg檔案包含定義記錄來源、資料轉換和匯出工具的參數。

您定義的轉換會處理Sensor( [!DNL .vsl] 檔案)或包含在文本檔案、XML檔案或ODBC相容的資料庫中，並將它們輸出到現有欄位、覆蓋當前資料或新定義的欄位中。

若要設定轉換功能，請編輯Data Workbench [!DNL Transform.cfg] 檔案（位於您要匯出事件資料的設定檔資料集資料夾中）。 此設定檔通常專用於轉換功能（亦即，您除了Data Workbench中定義的以外，不會執行其他資料處理） [!DNL Transform.cfg] 檔案)。 請務必注意， [!DNL Log Processing Dataset Include] 除了data workbench中指定的檔案外，還會套用任何繼承設定檔的檔案 [!DNL Transform.cfg] 檔案。

如需資料集包含檔案的相關資訊，請參閱 [資料集包含檔案](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

如果您要匯出的資料是由Data Workbench伺服器叢集處理，叢集中的每個處理伺服器(DPU)都會處理資料，但只會處理中的第一個DPU(處理伺服器#0) [!DNL profile.cfg] 檔案)將輸出資料寫入其本機檔案系統。

**若要編輯Data Workbench Transform.cfg檔案**

1. 在要匯出資料的設定檔中工作時，請開啟 [!DNL Profile Manager] 按一下 **[!UICONTROL Dataset]** 顯示目錄的內容。
1. 以滑鼠右鍵按一下Data Workbench旁的核取記號 [!DNL Transform.cfg]，然後按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Data Workbench [!DNL Transform.cfg] 的上界。
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
    <td colname="col2"> <p>選填。篩選資料以包含時間戳記最多但不包括的記錄項目。 Adobe建議您暫時使用下列其中一種格式： 
      <ul id="ul_C8C7F0F631594F7095CB83EF54E7CD0E"> 
       <li id="li_77AB6EEE8EEC4698AA886DE8BB0E2783"> 2013年1月1日HH:MM:SS EDT </li> 
       <li id="li_33806070F991476BB986906876CAF7F1"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定2013年7月29日00:00:美東夏令時 <span class="wintitle"> 結束時間 </span> 包括截至2013年7月28日、截至2013年7月11日:59:美國東部夏令時間下午59點。 </p> <p> 必須指定時區。 若未指定，時區不會預設為GMT。 如需Data Workbench伺服器支援的時區縮寫清單，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 時區代碼 </a>. </p> <p> 感測器和日誌檔案源的Use Start/End Times參數與此參數相關。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 出口商 </td> 
    <td colname="col2"> <p>導出器的子欄位指定輸出資料的處理和/或格式化方式。 您可以為一組日誌源定義多個導出器。 每個導出器類型都單獨建立輸出。 </p> <p> 存在三種類型的出口商： 
      <ul id="ul_C3C39F6DF3DC4F4CA2161EDB69599642"> 
       <li id="li_635FB271D0544D52B1C31740442D2E08"> ExportTextFile </li> 
       <li id="li_D496194848B44823A58890E03FFDD18E"> ExportDelimetedTextFile </li> 
       <li id="li_AEE9AA87076141FC91330D3FCFAB2101"> ExportVSLFile </li> 
      </ul> </p> <p> 有關導出器類型的詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-def-exp.md#task-900c40d1914347f288587bf0ca394ff2"> 定義匯出工具 </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 雜湊臨界值 </td> 
    <td colname="col2"> 選填。用於隨機行子採樣的採樣因子。 如果設為數字n，則每n個追蹤ID中只會選取一個以供匯出，將匯出的列總數減少n倍。若要匯出所有列，您可將雜湊臨界值設為1。 </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 記錄項目條件 </td> 
    <td colname="col2"> 選填。定義用於導出日誌條目的規則。 如需 <span class="wintitle"> 記錄項目條件 </span>，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 記錄處理組態檔 </a>. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 記錄來源 </td> 
    <td colname="col2"> <p>資料來源。 <span class="wintitle"> 記錄來源 </span> 可以 <span class="filepath"> .vsl </span> 檔案、日誌檔案或XML檔案或來自ODBC相容資料庫的資料。 如需有關 <span class="wintitle"> 記錄來源 </span>，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> 記錄處理組態檔 </a>. </p> <p> <span class="wintitle"> 轉換 </span> 預期所有來源資料在以字典排序的輸入檔案中按時間順序排列。 如果不滿足此要求，則「截止」計算不正確，並且可以在關閉輸出檔案之後處理附加輸入資料。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 離線模式 </td> 
    <td colname="col2"> <p>選填。True或False。 如果是真的， <span class="wintitle"> 轉換 </span> 假設所有輸入檔案在開始處理資料時都存在。 當所有輸入資料都被讀取時， <span class="wintitle"> 轉換 </span> 關閉所有輸出檔案，而不等待接收其他資料。 預設值為 false。 </p> <p> <p>注意：若 <span class="wintitle"> 離線模式 </span> 設為true, <span class="wintitle"> 轉換 </span> 預期處理開始前所有來源資料都會存在。 在 <span class="filepath"> VisualServer.log </span> 檔案（如果在關閉輸出檔案後收到其他資料）。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 重新處理 </td> 
    <td colname="col2"> <p>選填。您可以在此處輸入任何字元或字元組合。 變更此參數並將檔案儲存至 <span class="wintitle"> 轉換 </span> 電腦啟動資料重新處理。 </p> <p> 如需重新處理資料的詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新處理和重新轉換 </a>. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 階段 </td> 
    <td colname="col2"> <p>選填。可用於的處理階段名稱 <span class="wintitle"> 記錄處理資料集包含 </span> 除了data workbench以外執行的檔案 <span class="filepath"> Transform.cfg </span> 檔案。 處理階段提供了一種對中定義的轉換進行排序的方法 <span class="wintitle"> 記錄處理資料集包含 </span> 檔案。 如果您已在多個轉換中定義一或多個轉換，此參數將非常實用 <span class="wintitle"> 記錄處理資料集包含 </span> 檔案，並希望在導出過程中的特定點執行特定轉換。 </p> <p> 此處列出各階段的順序決定了 <span class="wintitle"> 記錄處理資料集包含 </span> 檔案會在資料匯出期間執行。 <span class="wintitle"> 預處理 </span> 和 <span class="wintitle"> 後處理 </span> 是內建階段； <span class="wintitle"> 預處理 </span> 總是第一階段， <span class="wintitle"> 後處理 </span> 永遠是最後一個階段。 依預設，會有一個名為的階段 <span class="wintitle"> 預設 </span>. </p> <p> <b>新增處理階段的方式</b> </p> 
      <ul id="ul_869C52DD30E443A496DC6363C3FC62B5"> 
       <li id="li_6493B2A335A8497C9A1BC6292C88CA81"> 在Data Workbench中 <span class="filepath"> Transform.cfg </span> 窗口，按一下右鍵 <span class="uicontrol"> 階段 </span>，然後按一下 <span class="uicontrol"> 新增 </span> &gt; <span class="uicontrol"> 階段 </span>. </li> 
       <li id="li_EE25E50CEB53450EA6465B08B0AE5442"> 輸入新階段的名稱。 </li> 
      </ul> <p> <b>刪除現有處理階段</b> </p> 
      <ul id="ul_4950BC26E0CD4837A4CB377605A52D3C"> 
      <li id="li_A61E2C17966E4F96A1256B8390623B0F"> 按一下右鍵與要刪除的階段對應的編號，然後按一下 <span class="uicontrol"> 移除 </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> <p> <p>注意：在 <span class="wintitle"> 記錄處理資料集包含 </span> 檔案的舞台名稱必須與您在此處輸入的名稱完全匹配。 如需資料集包含檔案的詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 資料集包含檔案 </a>. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 開始時間 </td> 
    <td colname="col2"> <p>選填。篩選資料以包含此時間或之後具有時間戳記的記錄項目。 Adobe建議您暫時使用下列其中一種格式： </p> 
      <ul id="ul_8F9B82A8AE7F45BE8C7949D2E96C7BEC"> 
       <li id="li_8F7BCFF251CB4F1B87DDA1A259FA9C7B"> 2013年1月1日HH:MM:SS EDT </li> 
       <li id="li_4BCE317EE1914074B3642687CFED5FC2"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> <p> 例如，指定2013年7月29日00:00:開始時間為美國東部夏令時間00美元包括從2013年7月29日起的12日資料:00:美國東部夏令時間上午00點。 </p> <p> 必須指定時區。 若未指定，時區不會預設為GMT。 如需Data Workbench伺服器支援的時區縮寫清單，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 時區代碼 </a>. </p> <p> <p>注意：感測器和日誌檔案源的Use Start/End Times參數與此參數相關。 </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> 轉換 </td> 
    <td colname="col2"> <p>選填。定義要套用至資料的轉換。 如需可用轉換類型的相關資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> 資料轉換 </a>. </p> <p> <p>注意：在Data Workbench中定義時，下列轉換類型無法運作 <span class="filepath"> Transform.cfg </span> 檔案： </p> </p> 
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
>如果在關閉輸出檔案後收到其他資料(請參閱 [!DNL Log Sources] 和 [!DNL Offline Mode] ), [!DNL Transform] 使用其他資料建立新的輸出檔案。 新輸出檔案的名稱從原始輸出檔案的名稱中生成，並在副檔名前面加上一個帶括弧的版本號。 例如，如果原始輸出檔案為 [!DNL 20070701-ABC.vsl]，此檔案的後續版本將命名為 [!DNL 20070701-ABC(1).vsl], [!DNL 20070701-ABC(2).vsl]等。 請注意，將版本控制檔案輸入Data Workbench伺服器可能會導致處理錯誤。
>
>
>Adobe建議避免建立版本化輸出檔案，方法是確保所有源資料在以字典排序的輸入檔案中按時間順序排列，如果 [!DNL Offline Mode] 設為true，表示處理開始前所有來源資料都存在。 如需詳細資訊，請參閱 [!DNL Log Sources] 和 [!DNL Offline Mode] 表中的條目。

1. 按一下右鍵添加轉換 **[!UICONTROL Transformations]** 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Transformation type]**. 完成轉換欄位。

   請參閱 [資料轉換](../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md) 有關可用於轉換功能的轉換的說明和示例。

1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端，按一下 **[!UICONTROL Save]**.
1. 若要讓本機所做的變更生效，請在 [!DNL Profile Manager]，以滑鼠右鍵按一下data workbench的勾號 [!DNL Transform.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**，其中profile name是要匯出資料之設定檔的名稱。 同步設定檔後，就會開始重新處理資料。

   >[!NOTE]
   >
   >如需重新處理資料以進行匯出的詳細資訊，請參閱 [重新處理和重新轉換](../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
