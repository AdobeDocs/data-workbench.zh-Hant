---
description: 編輯資料集描述檔之Log Processing.cfg檔案的步驟。
solution: Analytics
title: 編輯日誌處理配置檔案
topic: Data workbench
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 編輯日誌處理配置檔案{#editing-the-log-processing-configuration-file}

編輯資料集描述檔之Log Processing.cfg檔案的步驟。

1. 在資料集設定檔中工作時，請開啟並 [!DNL Profile Manager] 按一下以 **[!UICONTROL Dataset]** 顯示其內容。

   如需開啟和使用的詳細資訊 [!DNL Profile Manager]，請參閱資 *料工作台使用指南*。

   >[!NOTE]
   >
   >Dataset目錄中可能存在「日誌處理」子目錄。 此子目錄包含 [!DNL Log Processing Dataset Include] 已為一個或多個繼承的配置檔案建立的檔案。 請參閱 [資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 按一下右鍵旁邊的複選標 [!DNL Log Processing.cfg] 記並按一下 **[!UICONTROL Make Local]**。 此檔案的複選標籤將出現在列 [!DNL User] 中。
1. 以滑鼠右鍵按一下新建立的核取標籤，然後按一 **[!UICONTROL Open]** 下> **[!UICONTROL in Workstation]**。 出現 [!DNL Log Processing.cfg] 窗口。

   您也可以從 [!DNL Log Processing.cfg] 開啟檔案 [!DNL Transformation Dependency Map]。 有關轉換相關性映射的資訊，請參 [閱資料集配置工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

1. 使用下表作為指南編輯配置檔案中的參數。

   在資料工作台 [!DNL Log Processing.cfg] 視窗中編輯檔案時，您可以使用快速鍵進行基本編輯功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、復原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），並選取所有(Ctrl+a)。 您也可以使用快速鍵，將一個設定檔()的文字複製並貼到另 [!DNL .cfg]一個設定檔。

   >[!NOTE]
   >
   >繼承 [!DNL Log Processing Dataset Include] 的配置檔案包含下表中所述參數的子集以及一些其他參數。 請參閱 [資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

   <table id="table_BC7D3635C94049A9B608463AC1DBFA69">
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 參數 </th> 
      <th colname="col2" class="entry"> 說明 </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> 記錄來源 </td> 
      <td colname="col2"> 資料來源。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> 記錄來源 </a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 結束時間 </td> 
      <td colname="col2"> <p>選填。篩選資料以包含時間戳記最多但不包含此時間的記錄項目。 Adobe建議您目前使用下列其中一種格式： </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">2013年1月1日美國東部夏令時間 </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">2013年1月1日HH:MM:SS GMT </li> 
      </ul> <p>例如，指定「2013年7月29日美國東部夏令時間00:00:00」作為「結束時間」時，會包含截至2013年7月28日（美國東部夏令時間下午11:59:59）的資料。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選 </a>器。 </p> <p>您必須指定時區。 如果未指定，時區不預設為GMT。 如需資料工作台伺服器支援的時區縮寫清單，請參閱時區 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 代碼 </a>。 </p> <p> <p>注意： 感測器、日誌檔案和XML源的「使 <span class="wintitle"> 用 </span>開始／結束時間」參數與此參數相關。 請參閱「記錄來 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> 源」中討 </a> 論這些來源類型的章節。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 欄位 </td> 
      <td colname="col2"> 選填。Adobe建議在一或 <span class="wintitle"> 多個 </span> 記錄處理資料集 <span class="wintitle"> 中定義欄位包含 </span> 檔案。 請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> 記錄處理資料集包含檔 </a>案。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 組最大密鑰位元組數 </td> 
      <td colname="col2"> <p>伺服器可針對單一追蹤ID處理的事件資料量上限。 從資料集建構程式中篩選超過此限制的資料。 當鍵拆分處於活動狀態時，此值必須設定為2e6，當鍵拆分不活動時，此值必須設定為1e6。 請參 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> 閱密鑰分割 </a>。 </p> <p> <p>注意： 不要在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 雜湊閾值 </td> 
      <td colname="col2"> <p>選填。用於隨機行子採樣的採樣因子。 若設為數字n，則每n個追蹤ID中只有一個會進入資料集，將資料集中的列總數減少n倍。 </p> <p>若要建立需要100%正確率的資料集（亦即包含所有列），您可將雜湊臨界值設為1。 </p> <p>值: </p> <span class="filepath"> 雜湊臨界值= 1 </span> （100%的資料包含所有列）。 <p> <span class="filepath"> 雜湊臨界值= 2 </span> （資料的1/2，並包含一半的列）。 </p> <p> <span class="filepath"> 雜湊臨界值= 3 </span>（資料的1/3，並包含三列其中一列，但在「查詢完成」中四捨五入至34%） </p> <p> <span class="filepath"> 雜湊臨界值= 4 </span>（每4個資料中有1/4，並包含每4列1行。） </p> <p> </p> <p> <p>注意： 使用雜湊 <span class="filepath"> 閾值= 8可 </span> 提供1/8的資料，即12.5%。 不過， <span class="uicontrol"> 此值 </span> 的查詢完成值四捨五入為13%。 其他範例包 <span class="filepath"> 括雜湊臨界值= 6, </span> 可產生17%的查詢解析度。 雜湊 <span class="filepath"> 臨界值= 13可 </span>產生8%的查詢解析度。 </p> </p> <p>如果 <span class="wintitle"> 在Log Processing.cfg和 </span><span class="filepath"> Transformation.cfg檔案中都指定了「雜湊臨界值」，則 </span><span class="filepath"></span> 不會依序套用它；任一配置檔案中設定的最大值都適用。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選 </a>器。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 日誌條目條件 </td> 
      <td colname="col2"> 選填。定義將日誌條目納入資料集的規則。 請參 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 閱記錄條目條 </a>件。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 重新處理 </td> 
      <td colname="col2"> <p>選填。您可在此處輸入任何字元或字元組合。 更改此參數並將檔案保存到資料工作台伺服器電腦會啟動資料重新處理。 </p> <p>請參 <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 閱重新處理和重新轉 </a>換。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 分割關鍵時段空間 </td> 
      <td colname="col2"> <p>關鍵拆分涉及的參數。 當密鑰拆分處於活動狀態時，其值應為6e6。 請參 <a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split"> 閱密鑰分割 </a>。 </p> <p> <p>注意： 不要在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拆分鍵位元組 </td> 
      <td colname="col2"> <p>關鍵拆分涉及的參數。 當鍵拆分處於活動狀態時，其值應為1e6；當鍵拆分不活動時，其值應為0。 請參 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> 閱密鑰分割 </a>。 </p> <p> <p>注意： 不要在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拆分鍵空間比 </td> 
      <td colname="col2"> <p>關鍵拆分涉及的參數。 當鍵拆分處於活動狀態時，其值應為10。 請參 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> 閱密鑰分割 </a>。 </p> <p> <p>注意： 不要在未諮詢Adobe的情況下變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 階段 </td> 
      <td colname="col2"> <p>選填。可用於記錄處理資料集的處理階 <span class="wintitle"> 段名稱包括 </span> 檔案。 處理階段提供了一種對「日誌處理資料集包含」檔案中定 <span class="wintitle"> 義的轉換排序的 </span> 方法。 如果您已在多個日誌處理資料集包含檔案中定義了一個或多個轉換，並且希望在日誌處理過程中 <span class="wintitle"></span> 在特定點執行特定轉換，則此參數非常有用。 </p> <p>此處列出階段的順序決定了日誌處理資料集包含檔案中 <span class="wintitle"> 轉換在日誌處理 </span> 期間的執行順序。 預處理和後處理是內建階段。 預處理始終是第一階段，後處理則是最後階段。 依預設，有一個名為「預設」的命名階段。 </p> <p> <b>若要新增處理階段</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">在「 <span class="filepath"> Log Processing.cfg」視窗 </span> 中，以滑鼠右鍵按一下「 <span class="uicontrol"> Stages」（階段），然後按一下「Add </span> New <span class="uicontrol"></span><span class="uicontrol"></span>&gt; Stage」（新增&gt;階段）。 </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">輸入新階段的名稱。 </li> 
      </ul> </p> <p> <b>刪除現有處理階段</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">按一下右鍵要刪除的階段所對應的編號，然後按一下 <span class="uicontrol"> 刪 </span><i>除 <span class="uicontrol"> &lt; #stage_number </span>&gt;</i>。 </li> 
      </ul> </p> <p> <p>注意： 當您在「記錄處 <span class="wintitle"> 理資 </span> 料集包含檔案」中指定 <span class="wintitle"></span> 「舞台」時，舞台名稱必須與您在此處輸入的名稱完全相符。 請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 資料集包含檔 </a>案。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 開始時間 </td> 
      <td colname="col2"> <p>選填。篩選資料，以包含目前或之後具有時間戳記的記錄項目。 Adobe建議您目前使用下列其中一種格式： </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 2013年1月1日美國東部夏令時間 </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定「2013年7月29日美國東部夏令時間00:00:00」作為「開始時間」時，會包含從2013年7月29日美國東部夏令時間12:00:00開始的資料。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選 </a>器。 </p> <p> 您必須指定時區。 如果未指定，時區不預設為GMT。 如需資料工作台伺服器支援的時區縮寫清單，請參閱時區 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 代碼 </a>。 </p> <p> <p>注意： 感測器、日誌檔案和XML源的「使 <span class="wintitle"> 用 </span>開始／結束時間」參數與此參數相關。 請參閱「記錄來 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> 源」中討 </a> 論這些來源類型的章節。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 時區 </td> 
      <td colname="col2"> <p>選填。用於日誌處理期間時間轉換的資料工作台伺服器的時區（例如由x-local-timestring欄位表示的轉換）。 </p> <p> <p>注意： 如果要在資料集構建的日誌處理階段訪問轉換的時間欄位，則必須指定時區。 否則，資料工作台伺服器會在事件記錄檔中記錄錯誤。 </p> </p> <p>請參 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 閱時區 </a>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 轉換 </td> 
      <td colname="col2"> 選填。Adobe建議在一或多個記錄處理資料集包含檔案中，定 <span class="wintitle"> 義記錄處理的 </span> 轉換。 請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> 記錄處理資料集包含檔 </a>案。 </td> 
   </tr> 
   </tbody> 
   </table>

1. 按一下右鍵 **[!UICONTROL (modified)]** 窗口頂部，然後按一下 **[!UICONTROL Save]**。
1. 在中， [!DNL Profile Manager]按一下右鍵列中的復 [!DNL Log Processing.cfg]選 [!DNL User] 標籤，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]*** >使本地更改生效。 重新處理資料是在同步資料集描述檔後開始。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為當您安裝這些設定檔的更新時，會覆寫您所做的變更。

   如需重新處理資料的詳細資訊，請參閱重新 [處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
