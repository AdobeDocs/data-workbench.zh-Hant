---
description: 有關Report.cfg參數的資訊。
title: Report.cfg 參數
uuid: 7a20f4f6-99e6-401a-ba3c-c508881c0f0d
exl-id: 31e4de5f-f7e8-4a35-b5c6-6ad8ef79a259
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '2350'
ht-degree: 2%

---

# Report.cfg 參數{#report-cfg-parameters}

有關Report.cfg參數的資訊。

[Configure the Report Set](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)中顯示的範例[!DNL Report.cfg]預設僅包含[!DNL Report.cfg]檔案中包含的參數。 下表說明所有可用的[!DNL Report.cfg]檔案參數。

如果需要將其他參數添加到[!DNL Report.cfg]檔案，則必須使用文本編輯器進行添加。 如需相關步驟，包括如何定義每個參數項目的範例，請參閱[編輯現有Report.cfg檔案](../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887)。

>[!NOTE]
>
>此表中的參數按字母順序列出。 當您以Data Workbench開啟[!DNL Report.cfg]檔案時，向量會依字母順序列出，然後依字母順序列出個別參數。

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
   <td colname="col2"> <p><i>可選</i>. 此參數僅適用於具有量度指標的報表。 在傳送警報報告之前，必須出現在工作表中的度量指標數。 </p> <p>如果量度指標工作表中只監視一個量度，請將臨界值設為1。 當工作表中的量度評估為向上／向下箭頭或X時，就會產生報表。如果報表中監視了多個量度，您可以選取在產生報表之前必須評估為向上／向下箭頭或X的量度指標數。 例如，如果監視兩個量度： 
     <ul id="ul_A64E8A2306B14371A233D372B956F64D"> 
      <li id="li_2A3020ED350644A3954C36D3EB0B86D4">如果臨界值設為1，當工作表中的任一度量評估為向上／向下箭頭或X時，就會產生報表。 </li> 
      <li id="li_DA4EF4984880483DA48322D9D57B9240">如果臨界值設為2，則兩個量度在產生報表之前都必須評估為向上／向下箭頭或X。 </li> 
     </ul> </p> <p>如需度量指標的詳細資訊，請參閱<i>Data Workbench使用指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 允許報告再生 </td> 
   <td colname="col2"> <p>指出在您建立或修改這些報告時，<span class="keyword">報告伺服器</span>是否自動生成或重新生成特定報告。 選項是true或false。 如果設為true，則建立或修改報表工作區會使<span class="keyword">報表伺服器</span>重新產生最近執行的報表。 </p> <p> <p>注意： 變更<span class="filepath"> Report.cfg </span>檔案會使<span class="keyword">報表伺服器</span>重新產生由該<span class="filepath"> Report.cfg </span>檔案控制的所有報表。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 附件 </td> 
   <td colname="col2"> <p><i>可選</i>. 透過電子郵件分發之報表外出的任何附件名稱和內容類型的區段識別碼，包括附件數。 </p> <p>要添加新附件，請： 
     <ol id="ol_CBDC1E95D34A4D08A862680127438433"> 
      <li id="li_784C48C540534F4CBB35BBDA6BC5F48E">在Data Workbench中開啟<span class="filepath"> Report.cfg </span>檔案。 </li> 
      <li id="li_0709ADDDDF2E469FAB10761B46173136">按一下右鍵<span class="uicontrol">附件</span> ，然後按一下<span class="uicontrol">添加新子</span> &gt; <span class="uicontrol">附件</span>。 </li> 
     </ol> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 內容類型 </td> 
   <td colname="col2"> <p>要附加的檔案的內容類型。 </p> <p>範例：image/jpeg </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 檔案名 </td> 
   <td colname="col2"> <p>要附加的檔案的位置和名稱。 </p> <p>範例：<span class="filepath"> c:\myimage.jpg </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 顏色集 </td> 
   <td colname="col2"> 標識用於<span class="filepath"> .png </span>檔案的顏色配置。 0代表黑色背景；1代表白色背景；2代表灰階影像。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 執行命令 </td> 
   <td colname="col2"> <i>可選</i>. 產生報表集後執行的批次命令或可執行檔。 如果需要啟動命令shell解釋器，請在命令前面加上cmd /c。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預設Excel範本 </td> 
   <td colname="col2"> <p><i>可選</i>. 您要在將報表產生為Excel檔案時使用的一般Excel範本檔案（<span class="filepath"> .xls </span>或<span class="filepath"> .xlsx </span>）的檔案名稱。 此參數支援完整的檔案路徑，例如<span class="filepath"> c:\templates\mytemplate.xls </span>。 </p> <p>除非已為特定報表專門定義範本，否則此檔案會用於所有Excel報表。 請參閱<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751">使用範本檔案</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 維度名稱 </td> 
   <td colname="col2"> <i>可選</i>. 您要動態產生報表的維度名稱。 如果在此參數中輸入維度名稱，則必須在「查閱檔案」參數或「前N個量度」和「前N個值」參數中輸入值。 此參數中命名的維度必須存在於為其建立報表的資料集中。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 只有在完美時，才能以電子郵件傳送 </td> 
   <td colname="col2"> <i>可選</i>. 讓使用者指定報表集僅應在執行期間未發生錯誤時送出。 選項是true和false。 預設值為 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 結束日期 </td> 
   <td colname="col2"> <p><i>可選</i>. 您希望報表設定執行的最後日期和時間。 此時間以資料集的截止時間為基礎。 </p> <p>格式：MM/DD/YYYY hh:mm時區，使用24小時時間語法 </p> <p>範例：08/01/2007 12:01東部夏令時間 </p> <p>有關時區設定的詳細資訊，請參閱<i>資料集配置指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 每個 </td> 
   <td colname="col2"> 產生報表集的頻率：日、周或月。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Excel監視程式逾時（秒） </td> 
   <td colname="col2"> <p><i>可選</i>. 您希望<span class="keyword">報表伺服器</span>在<span class="keyword">報表伺服器</span>決定Excel未回應並終止程式之前，等待Microsoft Excel以Excel檔案產生報表的秒數。 使用此參數可讓<span class="keyword">報表伺服器</span>在Excel停止回應時終止，並繼續處理您的非Excel報表。 預設值為300.0。若要停用此功能，請將此參數設為0.0。 </p> <p>請確定您定義的值足夠長，以允許報表匯出至Excel。 否則，<span class="keyword">報表伺服器</span>可能會提早終止Excel，而您的報表將不會產生。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 篩選公式 </td> 
   <td colname="col2"> <p><i>可選</i>. 套用至報表集中每個工作區的篩選。 </p> <p>如需詳細資訊，請參閱建立篩選器</a>的<a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Filter_Expressions" format="http" scope="external">語法。 </a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma校正 </td> 
   <td colname="col2"> <p><span class="filepath"> .png </span>檔案輸出的Gamma設定。 預設值為 1.6。 </p> <p> <p>注意： Adobe建議您不要變更此值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 隱藏標誌 </td> 
   <td colname="col2"> 指出報表伺服器在產生報表時是否隱藏標誌。 選項為<span class="filepath"> true </span>或<span class="filepath"> false </span>。 如果設為<span class="filepath"> false </span>，則會以報表標誌產生報表。 預設值為<span class="filepath"> false </span>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 查閱檔案 </td> 
   <td colname="col2"> <p><i>可選</i>. 填入此參數後，報表伺服器會以動態模式執行，並針對Dimension名稱參數中指定之維度的每個元素產生報表。 此檔案必須包含兩個以Tab分隔的欄，不含標題列。 </p> <p> 
     <ul id="ul_378D4104BB5141C4A013EFE881BFFC6A"> 
      <li id="li_6F2C89A286B24FFE8EE8C82D278D0633">列1包含維元素清單。 </li> 
      <li id="li_4BD1CAA77FEC43268B40489BC5E5E6F7">第2欄包含報表收件者的電子郵件地址。 第1欄中指定元素的報表會傳送至第2欄中同一列的電子郵件地址。 您可以用逗號分隔多個電子郵件地址（無空格）。 如果不要以電子郵件傳送報表，此欄可以是空的，但必須存在。 </li> 
     </ul> </p> <p> <p>注意： 如果在此參數中輸入值，則必須在「Dimension名稱」參數中輸入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 僅通知 </td> 
   <td colname="col2"> 此<span class="wintitle">報表伺服器</span>設定可讓您設定資料工作台，以在產生報表時傳送電子郵件。 將此值設為<span class="filepath"> true </span>不會傳送報表，而是傳送電子郵件通知訂閱的使用者報表已產生。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 郵件報告 </td> 
   <td colname="col2"> <p>透過電子郵件分發報表的區段識別碼。 若要透過電子郵件分發報表，請填妥<span class="wintitle"> 「郵件報表</span>」項目的下列參數。 報表集中的所有報表都會以電子郵件傳送至「收件者」參數中指定的電子郵件地址。 </p> <p> <p>注意： 報表伺服器僅在產生至少一個報表時，才會傳送電子郵件。 </p> </p> <p>若要啟用報表的電子郵件傳送，您必須至少為此項目填妥下列參數： 
     <ul id="ul_539D64D61A8B4F1E95D889C6610EE3B8"> 
      <li id="li_D2EDBEE57BFE4FD4BB66F63AE561F1E2">SMTP伺服器 </li> 
      <li id="li_4EEFE6CDA3384FE38149CE8DCBEFF847">收件者 </li> 
      <li id="li_CF9F0CF7ECFC4D88A7F4F11BAC4938D6">發件人地址 </li> 
      <li id="li_40BFDCDC9640488EBB450CF8579DA250">僅通知 </li> 
     </ul> </p> <p> <p>注意： 若要在重新產生報表集後以電子郵件傳送報表，請參閱<a href="../../../home/c-rpt-oview/c-work-rpt-sets/c-edit-ex-rpt-files/c-edit-ex-rpt-files.md#concept-96fd57159f454defa09bd18655a12887">編輯現有的Report.cfg檔案</a>。 </p> </p> <p>5.4x和5.5x版本中提供「僅通知」值。 </p> <p>若要通知大量收件者（超過20位），強烈建議您使用電子郵件分發清單。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 內文XSL範本 </td> 
   <td colname="col2"> <p><i>可選</i>. 要應用到<span class="filepath"> reports.xml </span>檔案的XSL模板檔案的路徑。 使用此參數，報表伺服器可在分散式電子郵件中傳送您的報表，而非以附件形式傳送。 產生的文字會當做電子郵件訊息的正文。 </p> <p>如需範例檔案，請參閱<a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87">報表範例檔案</a>。 </p> <p>有關可擴展樣式表語言(XSLT)的資訊，請參見<a href="http://www.w3.org/Style/XSL/" format="http" scope="external">可擴展樣式表語言系列</a>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收件者 </td> 
   <td colname="col2"> 您要傳送報表之人員的電子郵件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 發件人地址 </td> 
   <td colname="col2"> 發件人的電子郵件地址。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 傳送者名稱 </td> 
   <td colname="col2"> 選填。發件人的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SMTP伺服器 </td> 
   <td colname="col2"> SMTP伺服器電腦的地址以及驗證所需的口令和用戶名。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 主旨 </td> 
   <td colname="col2"> <i>可選</i>. 描述要傳送之電子郵件的主旨行。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 僅通知 </td> 
   <td colname="col2"> 可讓您設定資料工作台，以便在產生背景報表時傳送電子郵件。 將此值設為True不會傳送報表，而是傳送電子郵件，將訂閱的使用者連結至報表位置。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出根 </td> 
   <td colname="col2"> <p><i>可選</i>. 產生的報表集的輸出位置。 預設值是「報告伺服器」安裝目錄中的<i>&lt;profile name&gt;</i>\Reports資料夾。 </p> <p>要配置<span class="keyword">報告伺服器</span>將報告輸出到入口網站，請將<span class="wintitle">輸出根</span>設定為用於入口網站的Web伺服器的文檔根。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預先載入查詢篩選 </td> 
   <td colname="col2"> <p><i>可選</i>. 此參數僅適用於<span class="wintitle"> 「頂級Dimension元素</span>」報表類型。 </p> <p>您要套用至查詢的篩選器名稱，此篩選器必須執行才能決定前N個維度元素，才能產生報表。 預設值為<span class="wintitle"> Broken_Session_Filter </span>。 有關<span class="wintitle">中斷會話過濾器</span>的詳細資訊，請參閱<i>Data Workbench使用手冊</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> 報告類型 </span> </td> 
   <td colname="col2"> <p>您要產生輸出的格式。 您可以使用下列任何或所有選項一次以多種格式輸出報表集： 
     <ul id="ul_FAF024F73F6B4F2C9D6760441E8F0CF9"> 
      <li id="li_04A3E0C7812B43E7BBFCDA8C3EA21CFC">Excel會建立每個工作表有一個視覺化的Excel活頁簿。 一般而言，使用Excel檔案進行電子郵件散發。 請參閱<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#concept-0b0fdb938805422d95c5f6fe706f09ee">將報表產生為Microsoft Excel檔案</a>。 有關使用模板檔案的資訊，請參閱<a href="../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-gen-rpts-ex-files.md#section-40ab11916f464b1a88214ab969da6751">使用模板檔案</a>。 </li> 
      <li id="li_CD1BDDEDE85349CE8C736887BB5E4726">png會建立可攜式網路圖形檔案。 一般而言，請使用<span class="filepath"> .png </span>檔案，以便顯示在網頁瀏覽器（入口網站）中。 </li> 
      <li id="li_869DA266E6A041A5BD343537743FAC79">縮圖會建立工作區的縮圖（<span class="filepath"> .jpg </span>檔案）。 預設大小為240x180。 若要變更預設大小，請編輯「縮圖X」和「縮圖Y」參數。 </li> 
     </ul> </p> <p>若要在資料工作台中編輯<span class="filepath"> Report.cfg </span>時新增報表類型，請以滑鼠右鍵按一下「<span class="uicontrol">報表類型</span>」，按一下「新增子系</span>」，然後選取所要的報表類型。<span class="uicontrol"> </span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 開始日期 </td> 
   <td colname="col2"> <p>您希望報表集執行的第一個日期和時間。 此時間以資料集的截止時間為基礎。 </p> <p>格式：MM/DD/YYY hh:mm時區，使用24小時語法表示時間。 </p> <p>有關時區設定的詳細資訊，請參閱<i>資料集配置指南</i>。 </p> <p> <p>注意： 當描述檔中資料的時間戳記符合指定的日期和時間時，報表就會開始執行。 </p> </p> <p>範例： </p> <p>如果開始日期是08/08/2006 12:00 EST，則報表會針對時間戳記為08/08/2006 12:00 EST及更新版本的資料執行。 
     <ul id="ul_EEF6F61B55E440DFB3348A9B10DFA5F1"> 
      <li id="li_133374F1287D4631BCAE7691E3FC93B6">每日報告將於08/08/2006執行，其後每天執行hh:mm = 12:00 EST的資料。 </li> 
      <li id="li_89514719C5F94D789E4A1049D2CD5F93">每週報告將於2006年8月08日執行，其後每7天執行一次，以取得EST為hh:mm = 12:00的資料。 </li> 
      <li id="li_EB986D04FA664DB89C66B0FC1CE4D36B">每月報表將於2006年8月8日執行，其後每月的8日執行，其中hh:mm = 12:00 EST的資料會執行。 </li> 
     </ul> </p> <p><span class="wintitle">報表時間</span>量度會影響「最近7天」、「昨天」和「3週前」等報表維度。 對於報表伺服器中的查詢，<span class="wintitle">報表時間</span>量度（<span class="filepath">報表時間。metric </span>）會識別報表執行的日期和時間。 這最初是在「開始日期」參數中指定的日期和時間，然後會依「每個」參數指定的期間遞增。 對於資料工作台中的查詢，<span class="wintitle">報表時間</span>量度是以「截止」量度的午夜（<span class="filepath">截止。metric </span>）為基礎。 由於「報表時間」量度的定義不同，如果您查詢使用「最後一個N」維度的工作區，您可以在相同工作區的資料工作台和<span class="keyword">報表伺服器</span>中收到不同的結果。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 縮圖X </td> 
   <td colname="col2"> <i>可選</i>. 控制輸出時生成的縮圖X軸大小（以像素為單位）的整數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 縮圖Y </td> 
   <td colname="col2"> <i>可選</i>. 控制輸出時生成的縮圖Y軸大小（以像素為單位）的整數。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 前N個量度 </td> 
   <td colname="col2"> <p><i>可選</i>. 請參閱「前N個值」參數的說明。 </p> <p> <p>注意： 如果在此參數中輸入值，則必須在「Dimension名稱」參數和「前N個值」參數中輸入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 前N個值 </td> 
   <td colname="col2"> <p><i>可選</i>. 填入此參數後，<span class="keyword">報表伺服器</span>會以動態模式執行，並針對「Dimension名稱」參數中指定之維度的元素排名（在此參數中指定）產生報表，依「前N個量度」參數中指定的量度計數。 </p> <p>範例：如果您在「Dimension名稱」參數中輸入「頁面」，在「前N個度量」參數中輸入「作業」，在此參數中輸入5，則產生的報表會列出作業數最多的五個排名最前的頁面。 </p> <p> <p>注意： 如果在此參數中輸入值，則必須在「Dimension名稱」參數和「前N個度量」參數中輸入值。 </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 僅使用本機範例 </td> 
   <td colname="col2"> <i>可選</i>. 指出您是否希望<span class="keyword">報表伺服器</span>僅使用資料集的本機範例產生報表。 將此參數設為true可讓您檢視報表集的範例（不需在資料工作台伺服器上載入），以檢視輸出的外觀，而不需花費一切時間來完全處理資料。 這會以測試函式運作。 選項是true或false。 預設值為false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作區路徑 </td> 
   <td colname="col2"> <p><i>可選</i>. 指定報表集的工作區集合位置。 這對於維護需要以多種方式產生和分發的單一工作區副本非常有用，它為多個報表集使用<span class="filepath"> Report.cfg </span>檔案。 此路徑的根目錄可以是任何配置檔案資料夾。 請勿在路徑字串的開頭輸入斜線(\)。 </p> <p>範例：您可以在<span class="filepath"> Reports\Common </span>資料夾中儲存「設定A」和「設定B」的常用工作區，然後為兩個不同的報表集定義<span class="filepath"> Report.cfg </span>檔案，每個報表集具有不同的層代和分佈設定。 在<span class="filepath"> Report.cfg </span>檔案中，您可將「工作區路徑」參數設為<i>描述檔名稱</i>\Reports\Common。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL輸出檔案 </td> 
   <td colname="col2"> <i>可選</i>. 將<span class="wintitle"> XSL模板</span>應用於報告索引時建立的輸出檔案的路徑。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> XSL範本 </td> 
   <td colname="col2"> <p><i>可選</i>. 要應用到報告索引的XSL模板檔案的路徑。 產生的轉換<span class="filepath"> .xml </span>會寫入指定的<span class="wintitle"> XSL輸出檔案</span>。 如需範例檔案，請參閱<a href="../../../home/c-rpt-oview/c-rpt-sample-files/c-rpt-sample-files.md#concept-a06b93f21c5d4888be335fa2281b2a87">報表範例檔案</a>。 </p> <p> <p>注意： 除非您在產生報表時使用<span class="filepath"> .xsl </span>範本，否則所有報表都會以電子郵件附件形式分發。 </p> </p> </td> 
  </tr> 
 </tbody> 
</table>
