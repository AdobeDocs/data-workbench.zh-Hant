---
description: Report.cfg參數的相關資訊。
title: Report.cfg 參數
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2348'
ht-degree: 2%

---

# Report.cfg 參數{#report-cfg-parameters}

{{eol}}

Report.cfg參數的相關資訊。

範例 [!DNL Report.cfg] 顯示於 [設定報表集](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0) 僅包含 [!DNL Report.cfg] 檔案。 下表提供所有可用 [!DNL Report.cfg] 檔案參數。

如果您需要新增其他參數至 [!DNL Report.cfg] 檔案時，必須使用文本編輯器執行此操作。 有關執行此操作的步驟，包括如何定義每個參數條目的示例，請參見 [編輯現有的Report.cfg檔案](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887).

>[!NOTE]
>
>此表中的參數按字母順序列出。 當您開啟 [!DNL Report.cfg] Data Workbench中，向量會以字母順序列出，接著以字母順序列出個別參數。

<table id="table_F55E925EA34F43B6832788BB6878BB4A">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 參數 </th>
   <th colname="col2" class="entry"> 說明 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> 警報閾值 </td>
   <td colname="col2"> <p><i>可選</i>. 此參數僅適用於具有量度指標的報表。 在傳送警報報表之前，必須出現在工作表中的量度指標數。 </p> <p>如果量度指標工作表中只監控一個量度，請將臨界值設為1。 當工作表中的度量評估為向上/向下箭頭或X時，即會生成報告。如果報告中監視了多個度量，則可以選擇在生成報告之前必須評估為向上/向下箭頭或X的度量指標數。 例如，如果正在監控兩個量度：
     <ul id="ul_A64E8A2306B14371A233D372B956F64D">
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">如果臨界值設為1，則當工作表中的其中一個量度評估為向上/向下箭頭或X時，即會產生報表。 </li>
      <li id="li_DA4EF4984880483DA48322D9D57B9240">如果臨界值設為2，在產生報表之前，這兩個量度都必須評估為向上/向下箭頭或X。 </li>
     </ul> </p> <p>如需量度指標的詳細資訊，請參閱 <i>Data Workbench使用手冊</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 允許重新產生報表 </td>
   <td colname="col2"> <p>指出 <span class="keyword"> 報表伺服器 </span> 在您建立或修改這些報表時，會自動產生或重新產生特定報表。 選項為true或false。 如果設為true，建立或修改報表工作區會造成 <span class="keyword"> 報表伺服器 </span> 以重新產生該報表以供最近執行。 </p> <p> <p>注意：變更 <span class="filepath"> Report.cfg </span> 檔案原因 <span class="keyword"> 報表伺服器 </span> 重新產生由 <span class="filepath"> Report.cfg </span> 檔案。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 附件 </td>
   <td colname="col2"> <p><i>可選</i>. 任何附件的名稱和內容類型的節標識符，這些附件與通過電子郵件分發的報告一起發出，包括附件數。 </p> <p>添加新附件：
     <ol id="ol_CBDC1E95D34A4D08A862680127438433">
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">開啟 <span class="filepath"> Report.cfg </span> 檔案Data Workbench。 </li>
      <li id="li_0709ADDDDF2E469FAB10761B46173136">按一下右鍵 <span class="uicontrol"> 附件 </span> 按一下 <span class="uicontrol"> 添加新子項 </span> &gt; <span class="uicontrol"> 附件 </span>. </li>
     </ol> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 內容類型 </td>
   <td colname="col2"> <p>要附加的檔案的內容類型。 </p> <p>範例：影像/jpeg </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 檔案名 </td>
   <td colname="col2"> <p>要附加的檔案的位置和名稱。 </p> <p>範例： <span class="filepath"> c:\myimage.jpg </span> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 色彩集 </td>
   <td colname="col2"> 識別要用於的色彩配置 <span class="filepath"> .png </span> 檔案。 0代表黑色背景；1代表白色背景；2用於灰度影像。 </td>
  </tr>
  <tr>
   <td colname="col1"> 要執行的命令 </td>
   <td colname="col2"> <i>可選</i>. 生成報告集後運行的批處理命令或執行檔。 如果需要啟動命令shell解釋器，請在命令前面加上cmd /c。 </td>
  </tr>
  <tr>
   <td colname="col1"> 預設Excel範本 </td>
   <td colname="col2"> <p><i>可選</i>. 通用Excel模板檔案的檔案名( <span class="filepath"> .xls </span> 或 <span class="filepath"> .xlsx </span>)，以Excel檔案產生報表時要使用的欄位。 此參數支援完整的檔案路徑，例如 <span class="filepath"> c:\templates\mytemplate.xls </span>. </p> <p>除非已針對特定報表專門定義範本，否則所有Excel報表都會使用此檔案。 請參閱 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> 使用範本檔案 </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 維度名稱 </td>
   <td colname="col2"> <i>可選</i>. 您要動態產生報表的維度名稱。 如果在此參數中輸入維度名稱，則必須在「查閱檔案」參數或「前N個量度」和「前N個值」參數中輸入值。 此參數中命名的維度必須存在於要建立報表的資料集中。 </td>
  </tr>
  <tr>
   <td colname="col1"> 只有在完美時才發送電子郵件 </td>
   <td colname="col2"> <i>可選</i>. 讓使用者指定只有在執行期間未發生錯誤時，才應傳送報表集。 選項為true和false。 預設值為 false。 </td>
  </tr>
  <tr>
   <td colname="col1"> 結束日期 </td>
   <td colname="col2"> <p><i>可選</i>. 您希望報表集執行的最後日期和時間。 這次是根據資料集的截止時間。 </p> <p>格式：MM/DD/YYYY hh:mm時區，使用24小時時間語法 </p> <p>範例：08/01/2007美國東部夏令時12時01分 </p> <p>如需時區設定的詳細資訊，請參閱 <i>資料集組態指南</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 每個 </td>
   <td colname="col2"> 報表集產生頻率：日、周或月。 </td>
  </tr>
  <tr>
   <td colname="col1"> Excel監視程式超時（秒） </td>
   <td colname="col2"> <p><i>可選</i>. 您想要的秒數 <span class="keyword"> 報表伺服器 </span> 在之前以Excel檔案產生報表時，等待Microsoft Excel回應 <span class="keyword"> 報表伺服器 </span> 決定Excel未回應，並終止程式。 使用此參數可啟用 <span class="keyword"> 報表伺服器 </span> 在Excel停止回應時終止，並繼續處理您的非Excel報表。 預設值為300.0。若要禁用此功能，請將此參數設定為0.0。 </p> <p>請確定您定義的值夠長，足以將報表匯出至Excel。 否則， <span class="keyword"> 報表伺服器 </span> 可能會提前終止Excel，而您的報表將不會產生。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 篩選公式 </td>
   <td colname="col2"> <p><i>可選</i>. 套用至報表集中每個工作區的篩選。 </p> <p>如需詳細資訊，請參閱 <a href="https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external"> 建立篩選器的語法 </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Gamma校正 </td>
   <td colname="col2"> <p>Gamma設定 <span class="filepath"> .png </span> 檔案輸出。 預設值為 1.6。 </p> <p> <p>注意：Adobe建議您不要變更此值。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 隱藏徽標 </td>
   <td colname="col2"> 指出報表伺服器在產生您的報表時是否隱藏標誌。 選項包括 <span class="filepath"> true </span> 或 <span class="filepath"> false </span>. 若設為 <span class="filepath"> false </span>，則報表會以「報表」標誌產生。 預設為 <span class="filepath"> false </span>. </td>
  </tr>
  <tr>
   <td colname="col1"> 查閱檔案 </td>
   <td colname="col2"> <p><i>可選</i>. 填入此參數時，報表伺服器會以動態模式執行，並為「Dimension名稱」參數中指定的維度的每個元素產生報表。 此檔案必須包含兩個以Tab分隔的欄，不含標題列。 </p> <p>
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A">
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">第1欄包含維度元素清單。 </li>
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">第2欄包含報表收件者的電子郵件地址。 第1欄中特定元素的報表會傳送至第2欄中同一列的電子郵件地址。 您可以用逗號分隔多個電子郵件地址（不含空格）。 如果不要以電子郵件傳送報表，此欄可以是空白的，但必須存在。 </li>
     </ul> </p> <p> <p>注意：如果在此參數中輸入值，則必須在「Dimension名稱」參數中輸入值。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 僅通知 </td>
   <td colname="col2"> 此 <span class="wintitle"> 報表伺服器 </span> 設定可讓您設定data workbench，以在產生報表時傳送電子郵件。 將此值設定為 <span class="filepath"> true </span> 不會傳送報表，而會傳送電子郵件，通知訂閱的使用者報表已產生。 </td>
  </tr>
  <tr>
   <td colname="col1"> 郵件報告 </td>
   <td colname="col2"> <p>透過電子郵件分送報表的區段識別碼。 若要透過電子郵件分發報表，請完成下列參數 <span class="wintitle"> 郵件報告 </span> 的下界。 報表集中的所有報表都會以一則訊息傳送至Recipients參數中指定的電子郵件地址。 </p> <p> <p>注意：報表伺服器僅在產生至少一個報表時才會傳送電子郵件。 </p> </p> <p>若要啟用報表的電子郵件傳送，您至少必須為此項目完成下列參數：
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8">
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP伺服器 </li>
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">收件者 </li>
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">寄件者地址 </li>
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">僅通知 </li>
     </ul> </p> <p> <p>注意：若要在重新產生報表集後以電子郵件傳送報表，請參閱 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887"> 編輯現有的Report.cfg檔案 </a>. </p> </p> <p>5.4x和5.5x版本提供「僅通知」值。 </p> <p>若要通知大量收件者（超過20個），強烈建議您使用電子郵件通訊組清單。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 內文XSL範本 </td>
   <td colname="col2"> <p><i>可選</i>. 要應用到的XSL模板檔案的路徑 <span class="filepath"> reports.xml </span> 檔案。 使用此參數可讓報表伺服器在分佈式電子郵件中傳送您的報表，而非以附件的形式傳送。 產生的文字會作為電子郵件訊息的內文。 </p> <p>請參閱 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> 報表範例檔案 </a> ，以取得範例檔案。 </p> <p>有關可擴展樣式表語言(XSLT)的資訊，請參見 <a href="https://www.w3.org/Style/XSL/" format="http" scope="external"> 可擴展樣式表語言系列 </a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 收件者 </td>
   <td colname="col2"> 您要傳送報表之對象的電子郵件地址。 </td>
  </tr>
  <tr>
   <td colname="col1"> 寄件者地址 </td>
   <td colname="col2"> 寄件者的電子郵件地址。 </td>
  </tr>
  <tr>
   <td colname="col1"> 寄件者名稱 </td>
   <td colname="col2"> 選填。寄件者的名稱。 </td>
  </tr>
  <tr>
   <td colname="col1"> SMTP伺服器 </td>
   <td colname="col2"> SMTP伺服器電腦的地址以及驗證所需的密碼和用戶名。 </td>
  </tr>
  <tr>
   <td colname="col1"> 主旨 </td>
   <td colname="col2"> <i>可選</i>. 說明要傳送之電子郵件的主旨行。 </td>
  </tr>
  <tr>
   <td colname="col1"> 僅通知 </td>
   <td colname="col2"> 可讓您設定Data Workbench，以在產生背景報表時傳送電子郵件。 將此值設為True不會傳送報表，而是傳送電子郵件，將訂閱的使用者連結至報表位置。 </td>
  </tr>
  <tr>
   <td colname="col1"> 輸出根 </td>
   <td colname="col2"> <p><i>可選</i>. 產生的報表集的輸出位置。 預設為 <i>&lt;profile name=""&gt;</i>\報告伺服器安裝目錄中的報告資料夾。 </p> <p>配置 <span class="keyword"> 報表伺服器 </span> 若要將報表輸出至入口網站，請設定 <span class="wintitle"> 輸出根 </span> 指向用於入口的web伺服器的文檔根目錄。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 預先載入查詢篩選器 </td>
   <td colname="col2"> <p><i>可選</i>. 此參數僅適用於 <span class="wintitle"> 排名在前的Dimension元素 </span> 報表類型。 </p> <p>您要套用至查詢的篩選器名稱，必須執行該篩選器以決定前N個維度元素，才能產生報表。 預設為 <span class="wintitle"> Broken_Session_Filter </span>. 如需 <span class="wintitle"> 中斷的工作階段篩選 </span>，請參閱 <i>Data Workbench使用手冊</i>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> <span class="wintitle"> 報告類型 </span> </td>
   <td colname="col2"> <p>要生成輸出的格式。 您可以使用下列任一或所有選項，一次以多種格式輸出報表集：
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9">
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel會建立一個Excel活頁簿，每個工作表各顯示一個視覺效果。 一般而言，請使用Excel檔案進行電子郵件分送。 請參閱 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee"> 以Microsoft Excel檔案產生報表 </a>. 如需使用範本檔案的詳細資訊，請參閱 <a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751"> 使用範本檔案 </a>. </li>
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png會建立可移植網路圖形檔案。 一般規則是使用 <span class="filepath"> .png </span> 要在網頁瀏覽器（入口網站）中顯示的檔案。 </li>
      <li id="li_869DA266E6A041A5BD343537743FAC79">縮圖會建立縮圖( <span class="filepath"> .jpg </span> 檔案)。 預設大小為240x180。 要更改預設大小，請編輯「縮圖X」和「縮圖Y」參數。 </li>
     </ul> </p> <p>編輯時新增報表類型的方式 <span class="filepath"> Report.cfg </span> 在data workbench中，按一下滑鼠右鍵 <span class="uicontrol"> 報表類型 </span>，按一下 <span class="uicontrol"> 添加新子項 </span>，然後選取所需的報表類型。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 開始日期 </td>
   <td colname="col2"> <p>您要報表集執行的第一個日期和時間。 這次是根據資料集的截止時間。 </p> <p>格式：MM/DD/YYY hh:mm時區，使用24小時語法表示時間。 </p> <p>如需時區設定的詳細資訊，請參閱 <i>資料集組態指南</i>. </p> <p> <p>注意：當設定檔中資料的時間戳記符合指定的日期和時間時，報表就會開始執行。 </p> </p> <p>範例: </p> <p>如果開始日期是東部標準08/08/2006 12:00 ，報表會針對時間戳記為08/08/2006 12:00（東部標準時間）及更新版本的資料執行。
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1">
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">每日報表會持續執行08/08/2006次，之後每天執行hh:mm = 12:00的資料。 </li>
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">對於東部標準時間為hh:mm = 12:00的資料，每週報告將運行08/08/2006，之後每7天運行一次。 </li>
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">每月報表的執行時間為08/08/2006，其後為每月的第8天，適用於東部標準時間hh:mm = 12:00的資料。 </li>
     </ul> </p> <p>此 <span class="wintitle"> 報表時間 </span> 量度會影響「最近N」報表維度，例如「最近7天」、「昨天」和「3週前」。 若是報表伺服器中的查詢， <span class="wintitle"> 報表時間 </span> 量度( <span class="filepath"> 報表時間.metric </span>)識別報表執行的日期和時間。 這最初是在「開始日期」參數中指定的日期和時間，然後以Every參數指定的期間為單位遞增。 若是Data Workbench中的查詢， <span class="wintitle"> 報表時間 </span> 量度以「截止」量度的午夜為基礎( <span class="filepath"> As Of.metric </span>)。 由於「報表時間」量度的定義不同，如果您查詢使用「最後N」維度的工作區，則可在Data Workbench和 <span class="keyword"> 報表伺服器 </span> 的URL區段。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 縮圖X </td>
   <td colname="col2"> <i>可選</i>. 控製作為輸出生成的縮圖X軸的大小（以像素為單位）的整數。 </td>
  </tr>
  <tr>
   <td colname="col1"> 縮圖Y </td>
   <td colname="col2"> <i>可選</i>. 控製作為輸出生成的縮圖Y軸大小（以像素為單位）的整數。 </td>
  </tr>
  <tr>
   <td colname="col1"> 前N個量度 </td>
   <td colname="col2"> <p><i>可選</i>. 請參閱前N個值參數的說明。 </p> <p> <p>注意：如果在此參數中輸入值，則必須在「Dimension名稱」參數和「前N個值」參數中輸入值。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 前N個值 </td>
   <td colname="col2"> <p><i>可選</i>. 填入此參數時， <span class="keyword"> 報表伺服器 </span> 以動態模式執行，並針對「Dimension名稱」參數中指定的維度，產生元素排名最前（在此參數中指定）的報表，依「排名最前的N個量度」參數中指定的量度計算。 </p> <p>範例：如果您在「Dimension名稱」參數中輸入「頁面」，在「前N個量度」參數中輸入「工作階段」，在此參數中輸入5，則產生的報表會列出工作階段數最多的前5個頁面。 </p> <p> <p>注意：如果您在此參數中輸入值，則必須在「Dimension名稱」參數和「前N個量度」參數中輸入值。 </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> 僅使用本地示例 </td>
   <td colname="col2"> <i>可選</i>. 指出您是否 <span class="keyword"> 報表伺服器 </span> 僅使用資料集的本機範例產生報表。 將此參數設為true，可讓您檢視報表集的範例（而不需在Data Workbench伺服器上載入），以查看輸出的外觀，而不需花費完全處理資料所需的所有時間。 這可作為測試函式運作。 選項為true或false。 預設值為false。 </td>
  </tr>
  <tr>
   <td colname="col1"> 工作區路徑 </td>
   <td colname="col2"> <p><i>可選</i>. 指定報表集的工作區集合位置。 對於維護需要以多種方式生成和分發的單個工作區副本，此功能非常有用，使用 <span class="filepath"> Report.cfg </span> 檔案。 此路徑的根目錄可以是任何配置檔案資料夾。 請勿在路徑字串的開頭輸入斜線(\)。 </p> <p>範例：可以為「設定A」和「設定B」儲存公共工作區，位於 <span class="filepath"> 報告\常見 </span> ，然後定義 <span class="filepath"> Report.cfg </span> 兩個不同報表集的檔案，每個報表集具有不同的層代和分發設定。 兩者皆適用 <span class="filepath"> Report.cfg </span> 檔案時，可將「工作區路徑」參數設定為 <i>設定檔名稱</i>\報告\常見。 </p> </td>
  </tr>
  <tr>
   <td colname="col1"> XSL輸出檔案 </td>
   <td colname="col2"> <i>可選</i>. 輸出檔案的路徑，此路徑是在 <span class="wintitle"> XSL範本 </span> 會套用至報表索引。 </td>
  </tr>
  <tr>
   <td colname="col1"> XSL範本 </td>
   <td colname="col2"> <p><i>可選</i>. 要應用到報表索引的XSL模板檔案的路徑。 所得的轉化 <span class="filepath"> .xml </span> 寫入指定 <span class="wintitle"> XSL輸出檔案 </span>. 請參閱 <a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87"> 報表範例檔案 </a> ，以取得範例檔案。 </p> <p> <p>注意：除非您使用 <span class="filepath"> .xsl </span> 範本產生報表時，所有報表都會以電子郵件附件形式分發。 </p> </p> </td>
  </tr>
 </tbody>
</table>
