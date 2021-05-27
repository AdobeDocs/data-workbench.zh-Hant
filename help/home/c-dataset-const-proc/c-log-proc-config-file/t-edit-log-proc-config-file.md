---
description: 編輯資料集設定檔之Log Processing.cfg檔案的步驟。
title: 編輯記錄處理組態檔
uuid: 2ffae53a-ef2f-4933-821d-13f29dcdb68d
exl-id: 294063ef-6771-4310-8198-df57fab1e2b4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1288'
ht-degree: 2%

---

# 編輯記錄處理組態檔{#editing-the-log-processing-configuration-file}

編輯資料集設定檔之Log Processing.cfg檔案的步驟。

1. 在資料集設定檔中工作時，請開啟[!DNL Profile Manager]並按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。

   有關開啟和使用[!DNL Profile Manager]的資訊，請參閱&#x200B;*Data Workbench使用手冊*。

   >[!NOTE]
   >
   >資料集目錄中可能有記錄處理子目錄。 此子目錄包含已為一個或多個繼承配置檔案建立的[!DNL Log Processing Dataset Include]檔案。 請參閱[資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

1. 按一下右鍵[!DNL Log Processing.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。
1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。 出現[!DNL Log Processing.cfg]窗口。

   您也可以從[!DNL Transformation Dependency Map]開啟[!DNL Log Processing.cfg]檔案。 如需轉換相依性映射的相關資訊，請參閱[資料集組態工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)。

1. 使用下表作為指南編輯配置檔案中的參數。

   在Data Workbench視窗中編輯[!DNL Log Processing.cfg]檔案時，您可以使用快速鍵來編輯基本的編輯功能，包括剪下(Ctrl+x)、複製(Ctrl+c)、貼上(Ctrl+v)、還原(Ctrl+z)、重做(Ctrl+Shift+z)、選取區段（按一下+拖曳），以及選取全部(Ctrl+a)。 您也可以使用捷徑將文字從一個組態檔([!DNL .cfg])複製並貼到另一個組態檔。

   >[!NOTE]
   >
   >繼承的配置檔案的[!DNL Log Processing Dataset Include]檔案包含下表中描述的參數的子集以及一些附加參數。 請參閱[資料集包含檔案](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)。

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
      <td colname="col2"> 資料來源。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea">記錄來源</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 結束時間 </td> 
      <td colname="col2"> <p>選填。篩選資料以包含時間戳記最多但不包含此時間的記錄項目。 Adobe建議您暫時使用下列其中一種格式： </p> 
      <ul id="ul_42613B1D2F3A4A6C9563BC9B54BE895E"> 
      <li id="li_BC6E5FC5CA204D89936845BE05DFE6E6">2013年1月1日HH:MM:SS EDT </li> 
      <li id="li_18FE1B0417AF4207B02497664F47D23F">2013年1月1日HH:MM:SS GMT </li> 
      </ul> <p>例如，將2013年7月29日00:00:00 EDT指定為「End Time（結束時間）」 ，包括截至2013年7月28日EDT 11:59:59下午的資料。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">資料篩選器</a>。 </p> <p>必須指定時區。 若未指定，時區不會預設為GMT。 如需Data Workbench伺服器支援的時區縮寫清單，請參閱<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">時區代碼</a>。 </p> <p> <p>注意： <span class="wintitle">感測器</span>、日誌檔案和XML源的Use Start/End Times參數與此參數相關。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea">日誌源</a>中討論這些源類型的部分。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 欄位 </td> 
      <td colname="col2"> 選填。Adobe建議在一或多個<span class="wintitle">記錄處理資料集包含</span>檔案中定義<span class="wintitle">欄位</span> 。 請參閱<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab">記錄處理資料集包含檔案</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 組最大密鑰位元組數 </td> 
      <td colname="col2"> <p>伺服器可針對單一追蹤ID處理的事件資料量上限。 超過此限制的資料會從資料集建構程式中篩選。 當密鑰拆分處於活動狀態時，此值必須設定為2e6；當密鑰拆分處於非活動狀態時，此值必須設定為1e6。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">鍵拆分</a>。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 雜湊臨界值 </td> 
      <td colname="col2"> <p>選填。用於隨機行子採樣的採樣因子。 如果設為數字n，則每n個追蹤ID中就只有一個會進入資料集，將資料集中的列數減少n倍。 </p> <p>若要建立需要100%準確度（即包含所有列）的資料集，您可將雜湊臨界值設為1。 </p> <p>值: </p> <span class="filepath"> 雜湊臨界值= 1 </span> （包含所有列的資料佔100%）。 <p> <span class="filepath"> 雜湊臨界值= 2 </span> （1/2的資料，且包含一半列）。 </p> <p> <span class="filepath"> 雜湊臨界值= 3( </span>資料的1/3，包含三列其中一列，但在查詢完成中四捨五入為34%) </p> <p> <span class="filepath"> 雜湊臨界值= 4( </span>資料的1/4，且包含四列中的一列)。 </p> <p> </p> <p> <p>注意： 使用<span class="filepath">雜湊臨界值= 8 </span>可提供1/8的資料，即12.5%。 不過，此值會捨入為13%的<span class="uicontrol">查詢完成</span>值。 其他範例包括雜湊臨界值= 6 </span>，可產生17%的查詢解析度。 <span class="filepath"><span class="filepath">雜湊臨界值= 13 </span>會產生8%的查詢解析度。 </span></p> </p> <p>如果在<span class="filepath"> Log Processing.cfg </span>和<span class="filepath"> Transformation.cfg </span>檔案中均指定了<span class="wintitle"> Hash Threshold </span> ，則不會依序應用該檔案；任一設定檔案中設定的最大值即適用。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">資料篩選器</a>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 記錄項目條件 </td> 
      <td colname="col2"> 選填。定義將記錄項目納入資料集的規則。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934">記錄項目條件</a>。 </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 重新處理 </td> 
      <td colname="col2"> <p>選填。您可以在此處輸入任何字元或字元組合。 變更此參數並將檔案儲存至Data Workbench伺服器電腦會起始資料重新處理。 </p> <p>請參閱<a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md">重新處理和重新轉換</a>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拆分鍵桶空間 </td> 
      <td colname="col2"> <p>密鑰拆分中涉及的參數。 密鑰拆分激活時，其值應為6e6。 請參閱<a href="/help/home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#key-split">鍵拆分</a>。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拆分鍵位元組 </td> 
      <td colname="col2"> <p>密鑰拆分中涉及的參數。 當密鑰拆分處於活動狀態時，其值應為1e6；當密鑰拆分處於非活動狀態時，其值應為0。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">鍵拆分</a>。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 拆分鍵空間比 </td> 
      <td colname="col2"> <p>密鑰拆分中涉及的參數。 當金鑰分割作用中時，其值應為10。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf">鍵拆分</a>。 </p> <p> <p>注意： 若沒有諮詢Adobe，請勿變更此值。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 階段 </td> 
      <td colname="col2"> <p>選填。可用於<span class="wintitle">記錄處理資料集包含</span>檔案的處理階段名稱。 處理階段提供了對<span class="wintitle">記錄處理資料集包含</span>檔案中定義的轉換進行排序的方法。 如果您已在多個<span class="wintitle">記錄處理資料集包含</span>檔案中定義了一或多個轉換，且您希望在記錄處理期間的特定時間點執行特定轉換，此參數將非常有用。 </p> <p>您在此列出階段的順序會決定在記錄處理期間執行<span class="wintitle">記錄處理資料集包含</span>檔案中轉換的順序。 預處理和後處理是內建階段。 預處理一律為第一階段，後處理則一律為最後階段。 預設情況下，有一個名為Default的命名階段。 </p> <p> <b>新增處理階段的方式</b> 
      <ul id="ul_3A49BEAD1C134344999FED379B8CE7A3"> 
         <li id="li_AFC9B2529EC64642AFF98E9D5BA88C71">在<span class="filepath"> Log Processing.cfg </span>窗口中，按一下右鍵<span class="uicontrol">階段</span> ，然後按一下<span class="uicontrol"> Add New </span> &gt; <span class="uicontrol"> Stage </span>。 </li> 
         <li id="li_5731B836658D4E1DB721C57C6275369A">輸入新階段的名稱。 </li> 
      </ul> </p> <p> <b>刪除現有處理階段</b> 
      <ul id="ul_BBF4F710A5624C578F1F2A38FE18E9AD"> 
         <li id="li_CF6982C752DE41FFA97759C30CDE6AA0">按一下右鍵要刪除的階段對應的編號，然後按一下<span class="uicontrol">刪除</span><i>&lt; <span class="uicontrol"> #stage_number </span></i>。 </li> 
      </ul> </p> <p> <p>注意： 在<span class="wintitle">記錄處理資料集包含</span>檔案中指定<span class="wintitle">階段</span>時，階段名稱必須與您在此輸入的名稱完全相符。 請參閱<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md">資料集包含檔案</a>。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 開始時間 </td> 
      <td colname="col2"> <p>選填。篩選資料以包含此時間或之後具有時間戳記的記錄項目。 Adobe建議您暫時使用下列其中一種格式： </p> <p> 
      <ul id="ul_0774889E22C24A6592809D289D1CBEC5"> 
         <li id="li_CE23541D8B584EA1AC432C5098564E46"> 2013年1月1日HH:MM:SS EDT </li> 
         <li id="li_2EB0CF60CF12444BB744E52E9C919152"> 2013年1月1日HH:MM:SS GMT </li> 
      </ul> </p> <p> 例如，將「2013年7月29日美國東部夏令時間00:00:00」指定為「開始時間」，包括從2013年7月29日美國東部夏令時間12:00:00點開始的資料。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d">資料篩選器</a>。 </p> <p> 必須指定時區。 若未指定，時區不會預設為GMT。 如需Data Workbench伺服器支援的時區縮寫清單，請參閱<a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477">時區代碼</a>。 </p> <p> <p>注意： <span class="wintitle">感測器</span>、日誌檔案和XML源的Use Start/End Times參數與此參數相關。 請參閱<a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea">日誌源</a>中討論這些源類型的部分。 </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 時區 </td> 
      <td colname="col2"> <p>選填。記錄處理期間，用於時間轉換的Data Workbench伺服器的時區（例如x-local-timestring欄位所代表的轉換）。 </p> <p> <p>注意： 如果您想要在資料集建構的記錄處理階段期間存取轉換的時間欄位，則必須指定時區。 否則，Data Workbench伺服器會在事件記錄中記錄錯誤。 </p> </p> <p>請參閱<a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956">時區</a>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 轉換 </td> 
      <td colname="col2"> 選填。Adobe建議在一個或多個<span class="wintitle">日誌處理資料集包含</span>檔案中定義日誌處理的轉換。 請參閱<a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab">記錄處理資料集包含檔案</a>。 </td> 
   </tr> 
   </tbody> 
   </table>

1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]** ，然後按一下&#x200B;**[!UICONTROL Save]**。
1. 在[!DNL Profile Manager]中，按一下右鍵[!DNL User]列中[!DNL Log Processing.cfg]的複選標籤，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL dataset profile name]**>* ，使本地所做的更改生效。 同步資料集設定檔後，就會開始重新處理資料。

   >[!NOTE]
   >
   >請勿將修改的設定檔儲存至Adobe提供的任何內部設定檔，因為您安裝這些設定檔的更新時，變更會遭到覆寫。

   如需重新處理資料的詳細資訊，請參閱[重新處理和重新轉換](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)。
