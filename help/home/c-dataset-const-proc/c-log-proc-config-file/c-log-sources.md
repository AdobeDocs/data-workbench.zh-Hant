---
description: 記錄來源是包含要用來建立資料集之資料的檔案。
title: 記錄來源
uuid: ea21c3d7-9188-4ba8-bacd-052d678bd799
exl-id: 36e0799b-197d-4c59-84ae-7a4350584ab1
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '3664'
ht-degree: 1%

---

# 記錄來源{#log-sources}

{{eol}}

記錄來源是包含要用來建立資料集之資料的檔案。

記錄來源中可用的資料稱為事件資料，因為每個資料記錄代表交易記錄或事件的單一例項。 Data Workbench伺服器可處理衍生自所收集資料的記錄來源 [!DNL Sensors] 或從其他資料來源擷取。

* **收集資料者 [!DNL Sensors]:**收集的資料 [!DNL Sensors] 從HTTP和應用程式伺服器傳送至Data Workbench伺服器，這些伺服器會將資料轉換為高度壓縮的記錄檔( [!DNL .vsl])檔案。 請參閱 [感測器檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009).

* **Insight Server擷取的資料：** Data Workbench伺服器會讀取一般檔案、XML檔案或符合ODBC的資料庫中包含的事件資料，並使用其解碼器來擷取所需資料的元素。 此類事件資料不必駐留在記憶體中，但包含資料的記錄必須包含追蹤ID。 請參閱 [記錄檔](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e), [XML日誌源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)，和 [ODBC資料源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3).

**添加日誌源**

1. 開啟 [!DNL Log Processing.cfg] 在data workbench中。
1. 按一下右鍵 **[!UICONTROL Log Sources]**，然後按一下 **[!UICONTROL Add New]**.

1. 選取下列其中一項：

   * **[!UICONTROL Sensor]**
   * **[!UICONTROL Log File]**
   * **[!UICONTROL XML Log Source]**
   * **[!UICONTROL ODBC Data Source]**

1. 定義資料集的特定參數會因資料集設定程式中使用的記錄來源類型而異。 指定與相應日誌源對應的部分中所示的參數：

   * [感測器檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)
   * [記錄檔](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)
   * [XML日誌源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)
   * [ODBC 資料來源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-odbc-data-sources.md#concept-5f2cf635081d44beab826ef5ec8cf4e3)

1. 在您定義了記錄來源（並對其他參數進行變更）後， [!DNL Log Processing.cfg] 檔案，將檔案儲存在本機，然後儲存至data workbench伺服器上的資料集設定檔。

   >[!NOTE]
   >
   >Data Workbench伺服器 [!DNL File Server Unit] 可接收和儲存 [!DNL Sensor] 檔案、記錄檔和XML檔案，並將它們提供至Data Workbench伺服器 [!DNL Data Processing Units] 來建構資料集。 請參閱 [設定Insight Server檔案伺服器單元](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d).

   您可以從 [!DNL Transformation Dependency Map]. 如需有關 [!DNL Transformation Dependency Map]，請參閱 [資料集組態設定工具](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

<!--
c_sensor_files.xml
-->

## 要求 {#section-d5901a4872774ad5bd01a18db114f1f2}

收集的事件資料 [!DNL Sensors] 從HTTP和應用程式伺服器傳送至Data Workbench伺服器，這些伺服器會將資料轉換為高度壓縮的記錄檔( [!DNL .vsl])檔案。 此 [!DNL .vsl] 檔案格式由data workbench伺服器管理，且每個檔案的名稱皆為：

YYYYMMDD-*SENSORID*.VSL

其中YYYYMMDD是檔案的日期，而 *SENSORID* 是名稱（由貴組織指派），可指出 [!DNL Sensor] 收集資料並傳送至data workbench伺服器。

## 參數 {#section-5c3f1e341c284486aeba3452057da7f3}

針對 [!DNL Sensor] 檔案中，可使用下列參數：

<table id="table_F583B475600041AFA3B9399AE0592146"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 記錄路徑 </td> 
   <td colname="col2"> <p>目錄 <span class="filepath"> .vsl</span> 檔案會儲存。 預設位置為Logs目錄。 相對路徑是指Data Workbench伺服器的安裝目錄。 </p> <p>您可以使用萬用字元來指定 <span class="filepath"> .vsl</span> 要處理的檔案： 
     <ul id="ul_AE144ED0FAB94FE8B32599A058659DE1"> 
      <li id="li_1E4E4CFD72C34B5EB71A3C59877950A9"> *符合任何字元數 </li> 
      <li id="li_4664400FC12E44B39B28438B85D20ED8"> ? 符合單一字元 </li> 
     </ul> </p> <p> 例如，日誌路徑 <span class="filepath"> 記錄檔\*.vsl</span> 匹配Logs目錄中結尾為 <span class="filepath"> .vsl</span>. 日誌路徑 <span class="filepath"> 日誌\*-SENSOR?.vsl</span> 與Logs目錄中的檔案匹配，其中包含任何日期(YYYYMMDD)，並且SENSOR（感測器1）後面有一個字元。 </p> <p> 如果要搜索指定路徑的所有子目錄，必須將Recursive參數設定為true。 </p> <p> <p>注意：如果要從Data Workbench伺服器的 <span class="wintitle"> 檔案伺服器單元</span>，則必須在「日誌路徑」參數中輸入相應的URI。 例如， <span class="filepath"> URI /Logs/*-*.vsl</span> 相符 <span class="filepath"> .vsl</span> 檔案。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌伺服器 </td> 
   <td colname="col2">連接到檔案伺服器所需的資訊（地址、名稱、埠等）。 如果日誌伺服器參數中有條目，則 <span class="wintitle"> 記錄路徑</span> 被解釋為URI。 否則，這些路徑會被解譯為本機路徑。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌源ID </td> 
   <td colname="col2"> <p>此參數的值可以是任何字串。 如果指定了值，此參數可讓您區分不同日誌源中的日誌條目，以用於源標識或目標處理。 x-log-source-id欄位中會填入一個值，用於識別每個記錄項目的記錄來源。 例如，如果您要識別 <span class="wintitle"> 感測器</span> 命名為VSensor01，您可以鍵入 <span class="filepath"> 從VSensor01</span>，而該字串將傳遞至該來源每個記錄項目的x-log-source-id欄位。 </p> <p> 如需x-log-source-id欄位的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> 事件資料記錄欄位</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 遞歸 </td> 
   <td colname="col2"> True或False。 若設為true，則中指定之每個路徑的所有子目錄 <span class="wintitle"> 記錄路徑</span> 搜索與指定檔案名或通配符模式匹配的檔案。 預設值為 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用開始/結束時間 </td> 
   <td colname="col2"> <p>True或False。 如果設定為true且指定了「開始時間」或「結束時間」，則此日誌源的所有檔案都必須具有以ISO格式(YYYYMMDD)的日期開始的檔案名。 假設每個檔案包含一GMT日的資料（例如，從一天0000 GMT開始，到次日0000 GMT結束的時間範圍）。 如果記錄來源檔案包含的資料不對應至GMT日，則必須將此參數設為false，以避免產生錯誤的結果。 </p> <p> <p>注意：依預設， <span class="filepath"> .vsl </span>包含收集資料的檔案 <span class="wintitle"> 感測器</span> 自動符合上述的命名和時間範圍需求。 如果將此參數設為true,Data Workbench伺服器一律會處理檔案中的資料，其名稱包含介於指定開始時間和結束時間之間的ISO日期。 如果將此參數設為false,Data Workbench伺服器會讀取 <span class="filepath"> .vsl</span> 記錄處理期間的檔案，以判斷哪些檔案包含「開始時間」和「結束時間」範圍內的資料。 </p> </p> <p> 如需「開始時間」和「結束時間」參數的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>請勿將設定參數用於 [!DNL Sensor] 資料來源，以決定應將記錄檔中的記錄項目納入資料集中。 請改為設定資料源，以指向目錄中的所有日誌檔案。 然後使用 [!DNL Log Processing.cfg] 以決定建構資料集時應使用的記錄項目。 請參閱 [資料篩選](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d).

<!--
c_log_files.xml
-->

包含事件資料的檔案必須符合下列要求：

* 檔案中的每個事件資料記錄都必須以一行表示。
* 記錄中的欄位必須以ASCII分隔字元分隔，無論是否空白。 Data Workbench伺服器不要求您使用特定分隔字元。 您可以使用非行尾字元且事件資料本身內未出現的任何字元。
* 檔案中的每個記錄都必須包含：

   * 追蹤ID
   * 時間戳

* 若要指定資料處理的開始和結束時間，每個檔案名稱必須為下列格式：

   * [!DNL YYYYMMDD-SOURCE.log]

   where *YYYYMMDD* 是檔案中所有資料的格林威治標準時間(GMT)天，而 *來源* 是識別檔案中所含資料來源的變數。

   >[!NOTE]
   >
   >請連絡Adobe諮詢服務，以檢閱您打算併入資料集的記錄檔。

## 參數 {#section-83a861ac24954d54bbb9530e4d8bf23c}

對於日誌檔案日誌源，下表中的參數可用。

>[!NOTE]
>
>處理日誌檔案日誌源需要在 [!DNL Log Processing Dataset Include] 檔案，其中包含 [!DNL Log Processing.cfg] 檔案，以及用於定義解碼器以從記錄檔擷取資料的特殊參數。 有關定義日誌檔案日誌源的解碼器的資訊，請參見 [文字檔案解碼器群組](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd).

<table id="table_F33735B5B90A48B0B21FA02D9198CCA9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 日誌檔案源的標識符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 記錄路徑 </td> 
   <td colname="col2"> <p>儲存日誌檔案的目錄。 預設位置為Logs目錄。 相對路徑是指Data Workbench伺服器的安裝目錄。 </p> <p> 您可以使用萬用字元來指定要處理的記錄檔： 
     <ul id="ul_1F02D26A08D846E2A3114E5C33F60ECF"> 
      <li id="li_ECAE1C03A1C448A1B86AE00B3A955708"> *符合任何字元數。 </li> 
      <li id="li_24FDB500C5934CAAA4124C435DF4B290"> ? 符合單一字元。 </li> 
     </ul> </p> <p> 例如，日誌路徑 <span class="filepath"> Logs\*.log</span> 匹配Logs目錄中結尾為 <span class="filepath"> .log</span>. </p> <p> 如果要搜索指定路徑的所有子目錄，則必須將Recursive參數設定為true。 </p> <p> 如果要從Data Workbench伺服器的 <span class="wintitle"> 檔案伺服器單元</span>，則必須在「日誌路徑」參數中輸入相應的URI。 例如， <span class="filepath"> URI/Logs/*.log</span> 相符 <span class="filepath"> .log</span> 檔案。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌伺服器 </td> 
   <td colname="col2"> 連接到檔案伺服器所需的資訊（地址、名稱、埠等）。 如果日誌伺服器參數中有條目，則 <span class="wintitle"> 記錄路徑</span> 被解釋為URI。 否則，這些路徑會被解譯為本機路徑。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 壓縮 </td> 
   <td colname="col2"> True或False。 如果Data Workbench伺服器要讀取的記錄檔是壓縮的gzip檔案，則此值應設為true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 解碼器群組 </td> 
   <td colname="col2"> 要套用至記錄檔記錄來源的文字檔案解碼器群組的名稱。 此名稱必須與 <span class="wintitle"> 記錄處理資料集包含</span> 檔案。 請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> 文字檔案解碼器群組</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌源ID </td> 
   <td colname="col2"> <p>此參數的值可以是任何字串。 如果指定了值，此參數可讓您區分不同日誌源中的日誌條目，以用於源標識或目標處理。 x-log-source-id欄位中會填入一個值，用於識別每個記錄項目的記錄來源。 例如，如果要從名為LogFile01的日誌檔案源中標識日誌條目，可以鍵入 <span class="filepath"> 從LogFile01</span>，而該字串將傳遞至該來源每個記錄項目的x-log-source-id欄位。 </p> <p> 如需x-log-source-id欄位的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> 事件資料記錄欄位</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 遮色片圖樣 </td> 
   <td colname="col2"> <p>具有單個捕獲子模式的規則表達式，它提取用於標識一系列日誌檔案源的一致名稱。 僅考慮檔案名。 規則運算式比對不會考慮路徑和擴充功能。 若您未指定 <span class="wintitle"> 遮罩圖案</span>，則會自動產生遮罩。 </p> <p> 對於檔案 <span class="filepath"> Logs\010105server1.log</span> 和 <span class="filepath"> Logs\010105server2.log</span>, <span class="wintitle"> 遮罩圖案</span> 會 <code>[0-9]{6}(.*)</code>. 此模式會從上述檔案名稱中擷取字串「server1」或「server2」。 </p> <p> 請參閱 <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> 規則運算式</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 遞歸 </td> 
   <td colname="col2"> True或False。 如果此參數設為true，則中指定之每個路徑的所有子目錄 <span class="wintitle"> 記錄路徑</span> 搜索與指定檔案名或通配符模式匹配的檔案。 預設值為 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 拒絕檔案 </td> 
   <td colname="col2"> 包含不符合解碼器條件之記錄項目之檔案的路徑與檔案名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用開始/結束時間 </td> 
   <td colname="col2"> <p>True或False。 如果此參數設定為true，並且指定了「開始時間」或「結束時間」，則此日誌源的所有檔案都必須具有以ISO格式(YYYYMMDD)的日期開始的檔案名。 假設每個檔案包含一GMT日的資料（例如，從一天0000 GMT開始，到次日0000 GMT結束的時間範圍）。 如果日誌源檔案名不以ISO日期開頭，或如果檔案包含的資料與GMT日期不對應，則必須將此參數設為false以避免結果不正確。 </p> <p> <p>注意：如果上述對日誌檔案的命名和時間範圍要求滿足，並且您將此參數設定為true，則指定的文本檔案解碼器組將讀取的檔案限制為那些名稱具有ISO日期且落在指定的開始時間和結束時間之間的檔案。 如果將此參數設為false,Data Workbench伺服器會在記錄處理期間讀取所有記錄檔，以判斷哪些檔案包含「開始時間」和「結束時間」範圍內的資料。 </p> </p> <p> 如需「開始時間」和「結束時間」參數的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

在此範例中，資料集是從兩種記錄來源建構。

日誌源0指定從捕獲的事件資料生成的日誌檔案 [!DNL Sensor]. 此資料源指向名為「日誌」的目錄，並指向該目錄中包含 [!DNL .vsl] 檔案名副檔名。

Log Source 1指向Logs目錄中的所有檔案，其中包含 [!DNL .txt] 檔案名副檔名。 此記錄來源的解碼器群組稱為「文字記錄」。

![](assets/cfg_LogProcessing_LogSources.png)

定義資料集的資料來源後，您不應刪除或移動記錄檔。 只應將新建立的日誌檔案添加到資料源的目錄中。

<!--
c_xml_log_sources.xml
-->

包含事件資料的檔案必須符合下列要求：

* 事件資料必須包含在格式正確的XML檔案中，且檔案具有適當的父子關係。
* 每個XML檔案格式必須有唯一的解碼器群組。 如需建構解碼器群組的相關資訊，請參閱 [XML解碼器群組](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).
* 檔案中的每個訪客記錄都必須包含：

   * 追蹤ID
   * 時間戳

* 若要指定資料處理的開始和結束時間，每個檔案名稱必須為

[!DNL YYYYMMDD-SOURCE.log]

where *YYYYMMDD* 是檔案中所有資料的格林威治標準時間(GMT)天，而 *來源* 是識別檔案中所含資料來源的變數。

有關滿足這些要求的XML檔案的示例，請參見 [XML解碼器群組](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

>[!NOTE]
>
>請連絡Adobe諮詢服務，以檢閱您打算併入資料集的XML記錄檔。

## 參數 {#section-d07b96d7f6ad4affb9cc0a0bc1b88c4d}

對於XML日誌源，下表中的參數可用。

>[!NOTE]
>
>處理XML日誌源需要在 [!DNL Log Processing Dataset Include] 檔案，其中包含 [!DNL Log Processing.cfg] 檔案以及用於定義解碼器以從XML檔案擷取資料的特殊參數。 有關定義XML日誌源的解碼器的資訊，請參見 [XML解碼器群組](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3).

<table id="table_86B849F379CF4FEBA9294ACEF8F55184"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 欄位 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> XML日誌源的標識符。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 記錄路徑 </td> 
   <td colname="col2"> <p>儲存XML日誌源的目錄。 預設位置為Logs目錄。 相對路徑是指Data Workbench伺服器的安裝目錄。 </p> <p> 您可以使用通配符指定要處理的XML日誌源： 
     <ul id="ul_0AE5D0ADE0F64CFAA856492A49239F58"> 
      <li id="li_4CBC0D1733F04258B3A55CC6FA714538 "> *符合任何字元數 </li> 
      <li id="li_81B597436A1241FF94E73C18A0ABBFA1"> ? 符合單一字元 </li> 
     </ul> </p> <p>例如，日誌路徑 <span class="filepath"> 日誌\*.xml</span> 匹配Logs目錄中結尾為 <span class="filepath"> .xml</span>. </p> <p> 如果要搜索指定路徑的所有子目錄，必須設定 <span class="wintitle"> 遞歸</span> 欄位設為true。 </p> <p> <p>注意：如果要從Data Workbench伺服器的 <span class="wintitle"> 檔案伺服器單元</span>，您必須在 <span class="wintitle"> 記錄路徑</span> 欄位。 例如， <span class="filepath"> URI/Logs/*.xml</span> 相符 <span class="filepath"> .xml</span> 檔案。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌伺服器 </td> 
   <td colname="col2"> 連接到檔案伺服器所需的資訊（地址、名稱、埠等）。 如果 <span class="wintitle"> 日誌伺服器</span> 欄位， <span class="wintitle"> 記錄路徑</span> 被解釋為URI。 否則，這些路徑會被解譯為本機路徑。 請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> 設定Insight Server檔案伺服器單元</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 壓縮 </td> 
   <td colname="col2"> True或False。 如果資料工作台伺服器要讀取的XML記錄來源是壓縮的gzip檔案，則此值應設為true。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 解碼器群組 </td> 
   <td colname="col2"> 要套用至XML記錄檔來源的XML解碼器群組名稱。 此名稱必須與 <span class="wintitle"> 記錄處理資料集包含</span> 檔案。 請參閱 <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> XML解碼器群組</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 日誌源ID </td> 
   <td colname="col2"> <p>此欄位的值可以是任何字串。 如果指定了值，則此欄位允許您區分不同日誌源中的日誌條目，以用於源標識或目標處理。 x-log-source-id欄位中會填入一個值，用於識別每個記錄項目的記錄來源。 例如，如果要標識名為XMLFile01的日誌檔案源中的日誌條目，可以鍵入 <span class="filepath"> 從XMLFile01</span>，而該字串將傳遞至該來源每個記錄項目的x-log-source-id欄位。 </p> <p> 如需x-log-source-id欄位的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md#concept-06bda4be1a4649a2905a4422e9e6c42f"> 事件資料記錄欄位</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 遮色片圖樣 </td> 
   <td colname="col2"> <p>具有單個捕獲子模式的規則表達式，它提取用於標識一系列日誌檔案源的一致名稱。 僅考慮檔案名。 規則運算式比對不會考慮路徑和擴充功能。 若您未指定 <span class="wintitle"> 遮罩圖案</span>，則會自動產生遮罩。 </p> <p> 對於檔案 <span class="filepath"> 日誌\010105server1.xml</span> 和 <span class="filepath"> 日誌\010105server2.xml</span>，蒙版圖案會是 <code>[0-9]{6}(.*)</code>. 此模式會從上述檔案名稱中擷取字串「server1」或「server2」。 </p> <p> 請參閱 <a href="../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c"> 規則運算式</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 遞歸 </td> 
   <td colname="col2"> True或False。 如果此參數設為true，則中指定之每個路徑的所有子目錄 <span class="wintitle"> 記錄路徑</span> 搜索與指定檔案名或通配符模式匹配的檔案。 預設值為 false。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 拒絕檔案 </td> 
   <td colname="col2"> 包含不符合解碼器條件之記錄項目之檔案的路徑與檔案名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用開始/結束時間 </td> 
   <td colname="col2"> <p>True或False。 如果此參數設定為true，並且指定了「開始時間」或「結束時間」，則此日誌源的所有檔案都必須具有以ISO格式(YYYYMMDD)的日期開始的檔案名。 假設每個檔案包含一GMT日的資料（例如，從一天0000 GMT開始，到次日0000 GMT結束的時間範圍）。 如果日誌源檔案名不以ISO日期開頭，或如果檔案包含的資料與GMT日期不對應，則必須將此參數設為false以避免結果不正確。 </p> <p> <p>注意：如果上述XML檔案的命名和時間範圍要求已滿足，並且您將此參數設定為true，則指定的XML解碼器組將讀取的檔案限制為那些名稱具有ISO日期且介於指定的開始時間和結束時間之間的檔案。 如果將此參數設為false,Data Workbench伺服器會在記錄處理期間讀取所有XML檔案，以判斷哪些檔案包含「開始時間」和「結束時間」範圍內的資料。 </p> </p> <p> 如需「開始時間」和「結束時間」參數的相關資訊，請參閱 <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> 資料篩選</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>定義資料集的資料來源後，您不應刪除或移動XML記錄來源。 只應將新建立的XML檔案添加到資料源的目錄中。

<!--
AVRO-log-file.xml
-->

Avro資料摘要提供更有效率的方式，將資料整合至Data Workbench:

<!-- <a id="section_45E3105B971C4220AE9CF573BEBF6080"></a> -->

* Avro為流量和商務資料提供單一來源格式。
* Avro摘要是每天提供多個來源區塊的壓縮資料。 它僅配置填入的欄位，並提供監控和通知功能、歷史資料的訪問以及自動恢復。
* 架構（自定義的Avro日誌檔案佈局）包含在每個檔案的開頭。
* 新增欄位並附有支援資訊，以內嵌Data Workbench資料，而不需要對解碼器進行任何變更。 這些類別包括：

   * Evar:1-250（原稱1-75）
   * 自訂事件：1-1000(1-100)
   * 存取行動、社交和視訊資料的解決方案變數

>[!NOTE]
>
>此外，使用Avro摘要可立即存取摘要中的任何新欄位，而不需關閉，因此可更新欄位，不需服務小時要求。

Avro資料饋送設定在個別檔案中：

* 安 **Avro日誌檔案**:這是從解碼器產生的Avro記錄格式，用以設定流量和商務資料的格式。
* 安 **Avro解碼器檔案**:此檔案可讓您將值對應至新的Avro格式。 您可以使用Avro解碼器精靈來設定解碼器。

## Avro解碼器精靈 {#section-9a824b4c3d5549e7952a7111232035b2}

此精靈會設定Avro解碼器記錄檔。

若要開啟，請在工作區中按一下滑鼠右鍵並選取 **管理** > **嚮導** > **Avro解碼器精靈**.

**步驟1:** **選擇Avro日誌檔案**.

在此步驟中，可以為Avro架構選擇源檔案。 可從記錄檔(.log)或現有的解碼器檔案(.avro)存取結構描述。 可從任一檔案提取結構描述。

| **Avro日誌檔案** | 按一下以開啟記錄檔(.log)檔案，以檢視記錄檔頂端的架構並產生解碼器檔案。 |
|---|---|
| **Avro解碼器檔案** | 按一下以開啟及編輯現有解碼器(.avro)檔案的結構。 |

**步驟2:選擇輸入欄位**.

選取要在資料集中使用的輸入欄位，以通過記錄處理。 檔案中的所有欄位都會顯示，供您選取摘要的欄位。

>[!NOTE]
>
>A [!DNL x-product(Generates row)] 如果資料中遇到陣列，則會提供欄位。 此欄位會為陣列中的巢狀資料產生新列，作為輸入欄位。 例如，如果陣列中有一個「點擊」列包含許多「產品」值，則會在輸入檔案中為每個產品產生列。

| **選擇預設值** | 選取要識別為標準預設欄位集的欄位。 |
|---|---|
| **選擇全部** | 選取檔案中的所有欄位。 |
| **取消選擇全部** | 清除檔案中的所有欄位。 |

**步驟3:選取要複製以產生列的欄位。**

因為新列可從陣列中的巢狀值建立，所以每個新建立的列都必須有追蹤ID和時間戳記。 此步驟可讓您選取要從父記錄複製到列的欄位，例如追蹤ID和時間戳記。 您也可以選取其他要新增至每一列的值。

| **選擇預設值** | 選取一組標準預設欄位，這些欄位需要新增新的欄值至每一列，例如追蹤ID和時間戳記。 例如， [!DNL hit_source] 欄位是新增至每個新列所需的預設值（在清單中定義為預設值）。 您可以視需要將其他欄值新增至每一列。 |
|---|---|
| **選擇全部** | 選取檔案中的所有欄位。 |
| **取消選擇全部** | 清除檔案中的所有欄位。 |

使用 **搜尋** 框中，可查找清單中的值。

**步驟4：指定解碼器名稱**

指派欄位群組的名稱並儲存為解碼器檔案。 名稱應符合記錄來源中指定的解碼器群組名稱。

**步驟5:儲存解碼器檔案。**

檔案功能表會開啟，為解碼器檔案命名並儲存為 [!DNL .cfg] 檔案 **記錄檔** 檔案夾。
