---
description: 編輯資料集描述檔的Transformation.cfg檔案的步驟。
solution: Analytics
title: 編輯轉換配置檔案
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 編輯轉換配置檔案{#editing-the-transformation-configuration-file}

編輯資料集描述檔的Transformation.cfg檔案的步驟。

1. 在資料集設定檔中工作時，請開啟並 [!DNL Profile Manager] 按一下以 **[!UICONTROL Dataset]** 顯示其內容。

   如需開啟和使用的詳細資訊 [!DNL Profile Manager]，請參閱資 *料工作台使用指南*。

   >[!NOTE]
   >
   >Transformation子目錄可能存在於Dataset目錄中。 此子目錄包含 [!DNL Transformation Dataset Include] 已為一個或多個繼承的配置檔案建立的檔案。 如需檔案的相 [!DNL Transformation Dataset Include] 關資訊，請參 [閱資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 按一下右鍵旁邊的複選標 [!DNL Transformation.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Workstation]**。 出現 [!DNL Transformation.cfg] 窗口。

   您也可以從 [!DNL Transformation.cfg] 開啟檔案 [!DNL Transformation Dependency Map]。 如需相關資訊， [!DNL transformation dependency maps]請參閱資 [料集設定工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

1. 使用下表作為指南編輯配置檔案中的參數。

   在資料工作台 [!DNL Transformation.cfg] 視窗中編輯檔案時，您可使用快速鍵進行基本編輯功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），並選取所有(Ctrl+a)。 此外，您也可以使用捷徑，將一個設定檔()的文字複製並貼到另 [!DNL .cfg]一個設定檔。

   >[!NOTE]
   >
   >繼承 [!DNL Transformation Dataset Include] 的配置檔案包含下表中所述參數的子集以及一些其他參數。 如需檔案的相 [!DNL Transformation Dataset Include] 關資訊，請參 [閱資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
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
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 2013年1月1日美國東部夏令時間 </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定「2013年7月29日美國東部夏令時間00:00:00」作為「結束時間」，會包含2013年7月28日美國東部夏令時間11:59:59的資料。 </p> <p> 您必須指定時區。 如果未指定，時區不預設為GMT。 如需資料工作台伺服器支援的時區縮寫清單，請參閱時區 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 代碼 </a>。 </p> <p> <p>注意： 如果您指定「結束時間」的值，則會在資料集建構的轉換階段中設定並套用名為「結束時間」的參數。 如需參數的詳細資訊，請參 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 閱在資料集包含檔案中定義參數 </a>。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 延伸尺寸 </td> 
      <td colname="col2"> 選填。Adobe建議在一或多個轉換資料集包含檔案 <span class="wintitle"> 中定義擴充 </span> 維度。 如需詳細資訊，請參 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 閱轉換資料集包含檔 </a>案。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 雜湊閾值 </td> 
      <td colname="col2"> <p>選填。用於隨機行子採樣的採樣因子。 若設為數字n，則每n個追蹤ID中只有一個會進入資料集，將資料集中的列總數減少n倍。若要建立需要100%正確率的資料集（亦即包含所有列），您可將雜湊臨界值設為1。 </p> <p> 如果Log Processing.cfg和 <span class="filepath"> Transformation.cfg檔案中都指定了Hash Threshold（散列閾值），則不 </span><span class="filepath"></span> 會按順序應用它；應用任一配置檔案中設定的最大值。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 日誌條目條件 </td> 
      <td colname="col2"> 選填。定義規則，根據該規則，日誌處理輸出的日誌條目將被視為包含在資料集配置檔案中。 請參 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 閱記錄條目條 </a>件。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 新訪客條件 </td> 
      <td colname="col2"> 選填。用於網頁資料。 定義將訪客納入資料的規則。 「 <span class="wintitle"> 新訪客條 </span> 件」定義資料集中要使用之訪客的第一個記錄項目（依時間排序）。 此訪客的所有後續記錄項目都會納入資料集中，不論其是否符合此條件。 請參閱 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> 新訪客條件 </a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 重新處理 </td> 
      <td colname="col2"> <p>選填。您可在此處輸入任何字元或字元組合。 更改此參數並保存檔案會啟動資料重新轉換。 </p> <p> 如需重新處理資料的詳細資訊，請參閱重新 <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 處理和重新轉換 </a>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 方案檢查 </td> 
      <td colname="col2"> 是非。 如果為true，則資料工作台伺服器會識別資料集損壞問題，並在資料工作台伺服器的「跟蹤」目錄中記錄有關日誌檔案中問題的資訊。 預設值為true。 Adobe建議您隨時將此參數設為true。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 階段 </td> 
      <td colname="col2"> <p>選填。可用於轉換資料集的處理階段的名 <span class="wintitle"> 稱包括文 </span> 件。 處理階段提供了對「轉換資料集包括」檔案中定義的轉換 <span class="wintitle"> 排序的 </span> 方法。 如果在多個轉換資料集包含檔案中定義了一個或多個轉換，並且希望在轉換過程中在特定點執行特 <span class="wintitle"></span> 定轉換，則此參數非常有用。 </p> <p> 在此處列出階段的順序決定了轉換資料集包含檔案中轉換在轉換期 <span class="wintitle"> 間執行 </span> 的順序。 <span class="wintitle"> 預處理 </span> 和 <span class="wintitle"> 後處理 </span> 是內置的階段；預 <span class="wintitle"> 處理 </span> 總是第一個階段，後處理 <span class="wintitle"></span> 總是最後一個階段。 依預設，有一個名為「預設」的命 <span class="wintitle"> 名階段 </span>。 </p> <p> <b>若要新增處理階段</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> 在「 <span class="filepath"> Transformation.cfg」窗 </span> 口中，按一下右鍵「階段」 ，然後按一下「添加新 <span class="uicontrol"> 的階段」 </span> &gt; 「 <span class="uicontrol"></span><span class="uicontrol"></span>Trasformation」。 </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> 輸入新階段的名稱。 </li> 
      </ul> </p> <p> <b>刪除現有處理階段</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> 按一下右鍵要刪除的階段所對應的編號，然後按一下 <span class="uicontrol"> 刪 </span><i>除 <span class="uicontrol"> &lt; #stage_number </span>&gt;</i>。 </li> 
      </ul> </p> <p> <p>注意： 在轉換資料集包含檔案中指 <span class="wintitle"> 定舞台時， </span> 舞台的名稱必須與在此處輸入的名稱完全匹配。 如需資料集包含檔案的詳細資訊，請參閱資料集 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 包含檔案 </a>。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 開始時間 </td> 
      <td colname="col2"> <p>選填。篩選資料，以包含目前或之後具有時間戳記的記錄項目。 Adobe建議您目前使用下列其中一種格式： 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 2013年1月1日美國東部夏令時間 </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，將2013年7月29日美國東部夏令時間指定為00:00:00（美國東部夏令時間） <span class="wintitle"></span> ，包括從2013年7月29日美國東部夏令時間12:00:00開始的資料。 </p> <p> 您必須指定時區。 如果未指定，時區不預設為GMT。 如需資料工作台伺服器支援的時區縮寫清單，請參閱時 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 區代碼 </a>。 </p> <p> <p>注意： 如果您指定「開始時間」的值，則會在資料集建構的轉換階段中設定並套用名為「開始時間」的參數。 如需參數的詳細資訊，請參 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 閱在資料集包含檔案中定義參數 </a>。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 轉換 </td> 
      <td colname="col2"> 選填。Adobe建議在一或多個「轉換資料集包含」檔案中定義資料集建構的 <span class="wintitle"> 轉換階段 </span> 轉換。 如需詳細資訊，請參 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 閱轉換資料集包含檔 </a>案。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 時區 </td> 
      <td colname="col2"> <p>資料集描述檔的時區。 時區用於時間轉換和建立時間維度。 請參 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 閱時區 </a>。 </p> <p> <p>注意： 在「記錄處理 <span class="filepath"> .cfg」檔案中定 </span> 義時，「時區」參數僅用於時間轉換。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。
1. 在中， [!DNL Profile Manager]以滑鼠右鍵按一下欄 [!DNL Transformation.cfg]中的 [!DNL User] 核取標籤，然後按一下 **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** ，讓本機所做的變更生效。 資料集描述檔的同步後，開始重新轉換資料。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

   如需重新處理或重新轉換資料的詳細資訊，請參閱重新 [處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
