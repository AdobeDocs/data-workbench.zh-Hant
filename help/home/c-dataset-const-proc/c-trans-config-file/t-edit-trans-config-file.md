---
description: 編輯資料集設定檔之Transformation.cfg檔案的步驟。
title: 編輯轉換組態檔
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---

# 編輯轉換組態檔{#editing-the-transformation-configuration-file}

{{eol}}

編輯資料集設定檔之Transformation.cfg檔案的步驟。

1. 使用資料集設定檔時，請開啟 [!DNL Profile Manager] 按一下 **[!UICONTROL Dataset]** 來顯示其內容。

   如需開啟和使用的相關資訊 [!DNL Profile Manager]，請參閱 *Data Workbench使用手冊*.

   >[!NOTE]
   >
   >資料集目錄中可能有轉換子目錄。 此子目錄包含 [!DNL Transformation Dataset Include] 已為一個或多個繼承的配置檔案建立的檔案。 如需有關 [!DNL Transformation Dataset Include] 檔案，請參閱 [資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. 以滑鼠右鍵按一下旁的核取記號 [!DNL Transformation.cfg] 按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。
1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. 此 [!DNL Transformation.cfg] 的上界。

   您也可以開啟 [!DNL Transformation.cfg] 檔案來自 [!DNL Transformation Dependency Map]. 如需有關 [!DNL transformation dependency maps]，請參閱 [資料集組態設定工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. 使用下表作為指南編輯配置檔案中的參數。

   編輯 [!DNL Transformation.cfg] 檔案時，您可以使用快速鍵來編輯基本功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、還原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取全部(Ctrl+a)。 此外，您可以使用捷徑來複製和貼上來自一個設定檔案的文字( [!DNL .cfg])到其他。

   >[!NOTE]
   >
   >A [!DNL Transformation Dataset Include] 繼承的配置檔案包含下表中描述的參數的子集以及一些附加參數。 如需有關 [!DNL Transformation Dataset Include] 檔案，請參閱 [資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

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
      <td colname="col2"> <p>選填。篩選資料以包含時間戳記最多但不包括的記錄項目。 Adobe建議您暫時使用下列其中一種格式： 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 2013年1月1日HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定「2013年7月29日」:00:「結束時間」包括截至2013年7月28日（即11日）的資料:59:美國東部夏令時間下午59點。 </p> <p> 必須指定時區。 若未指定，時區不會預設為GMT。 如需Data Workbench伺服器支援的時區縮寫清單，請參閱 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 時區代碼 </a>. </p> <p> <p>注意：如果您指定「結束時間」的值，系統會在資料集建構的轉換階段中設定並套用名為「結束時間」的參數。 如需參數的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 定義資料集包含檔案中的參數 </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 延伸維度 </td> 
      <td colname="col2"> 選填。Adobe建議在一或多個維度中定義延伸維度 <span class="wintitle"> 轉換資料集包含 </span> 檔案。 如需詳細資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 轉換資料集包含檔案 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 雜湊臨界值 </td> 
      <td colname="col2"> <p>選填。用於隨機行子採樣的採樣因子。 如果設為數字n，則每n個追蹤ID中就只有一個會進入資料集，將資料集中的列數減少n倍。若要建立需要100%準確度（即包含所有列）的資料集，您可將雜湊臨界值設為1。 </p> <p> 若已在 <span class="filepath"> Log Processing.cfg </span> 和 <span class="filepath"> Transformation.cfg </span> 檔案，則不會依序套用；任一設定檔案中設定的值上限即適用。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 記錄項目條件 </td> 
      <td colname="col2"> 選填。定義規則，根據此規則，記錄處理中輸出的記錄項目會納入資料集設定檔中。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> 記錄項目條件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 新訪客條件 </td> 
      <td colname="col2"> 選填。用於Web資料。 定義將訪客視為包含在資料中的規則。 此 <span class="wintitle"> 新訪客條件 </span> 會定義資料集中所使用之訪客的第一個記錄項目（依時間排序）。 無論該訪客是否符合此條件，其所有後續記錄項目都會納入資料集中。 請參閱 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> 新訪客條件 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 重新處理 </td> 
      <td colname="col2"> <p>選填。您可以在此處輸入任何字元或字元組合。 變更此參數並儲存檔案會起始資料重新轉換。 </p> <p> 如需重新處理資料的詳細資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> 重新處理和重新轉換 </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 架構檢查 </td> 
      <td colname="col2"> True或False。 若為true，則Data Workbench伺服器會識別資料集損毀問題，並在Data Workbench伺服器的「追蹤」目錄中記錄記錄檔中有關問題的資訊。 預設值為true。 Adobe建議您隨時將此參數設為true。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 階段 </td> 
      <td colname="col2"> <p>選填。可用於的處理階段名稱 <span class="wintitle"> 轉換資料集包含 </span> 檔案。 處理階段提供了一種對中定義的轉換進行排序的方法 <span class="wintitle"> 轉換資料集包含 </span> 檔案。 如果您已在多個轉換中定義一或多個轉換，此參數將非常實用 <span class="wintitle"> 轉換資料集包含 </span> 檔案，並希望在轉換期間在特定點執行特定轉換。 </p> <p> 此處列出各階段的順序決定了 <span class="wintitle"> 轉換資料集包含 </span> 檔案會在轉換期間執行。 <span class="wintitle"> 預處理 </span> 和 <span class="wintitle"> 後處理 </span> 是內建階段； <span class="wintitle"> 預處理 </span> 總是第一階段， <span class="wintitle"> 後處理 </span> 永遠是最後一個階段。 依預設，會有一個名為的階段 <span class="wintitle"> 預設 </span>. </p> <p> <b>新增處理階段的方式</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> 在 <span class="filepath"> Transformation.cfg </span> 窗口，按一下右鍵 <span class="uicontrol"> 階段 </span> 按一下 <span class="uicontrol"> 新增 </span> &gt; <span class="uicontrol"> 階段 </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> 輸入新階段的名稱。 </li> 
      </ul> </p> <p> <b>刪除現有處理階段</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> 按一下右鍵與要刪除的階段對應的編號，然後按一下 <span class="uicontrol"> 移除 </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>注意：在 <span class="wintitle"> 轉換資料集包含 </span> 檔案舞台的名稱必須與您在此處輸入的名稱完全匹配。 如需資料集包含檔案的詳細資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> 資料集包含檔案 </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 開始時間 </td> 
      <td colname="col2"> <p>選填。篩選資料以包含此時間或之後具有時間戳記的記錄項目。 Adobe建議您暫時使用下列其中一種格式： 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 2013年1月1日HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，指定2013年7月29日00:00:美東夏令時 <span class="wintitle"> 開始時間 </span> 包括2013年7月29日起，於:00:美國東部夏令時間上午00點。 </p> <p> 必須指定時區。 若未指定，時區不會預設為GMT。 如需Data Workbench伺服器支援的時區縮寫清單，請參閱 <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> 時區代碼 </a>. </p> <p> <p>注意：如果您指定「開始時間」的值，系統會在資料集建構的轉換階段中設定並套用名為「開始時間」的參數。 如需參數的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> 定義資料集包含檔案中的參數 </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 轉換 </td> 
      <td colname="col2"> 選填。Adobe建議在一或多個資料集建構的轉換階段中定義轉換 <span class="wintitle"> 轉換資料集包含 </span> 檔案。 如需詳細資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> 轉換資料集包含檔案 </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 時區 </td> 
      <td colname="col2"> <p>資料集設定檔的時區。 時區用於時間轉換和建立時間維度。 請參閱 <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> 時區 </a>. </p> <p> <p>注意：若定義於 <span class="filepath"> Log Processing.cfg </span> 時區參數僅用於時間轉換。 </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端按一下 **[!UICONTROL Save]**.
1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL Transformation.cfg]在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** 使本地更改生效。 同步資料集設定檔後，即會開始重新轉換資料。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

   如需重新處理或重新轉換資料的相關資訊，請參閱 [重新處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
