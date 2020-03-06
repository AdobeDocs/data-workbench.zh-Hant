---
description: 出口商提供輸出事件資料的指示。
solution: Analytics
title: 定義出口商
topic: Data workbench
uuid: 565d4482-6c25-407c-bda7-0d116180902a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 定義出口商{#defining-exporters}

出口商提供輸出事件資料的指示。

轉換功能提供三種類型的輸出器 [!DNL .vsl][!DNL .vsl] ，可將檔案、日誌檔案、XML檔案和ODBC資料導出為檔案、文本檔案或分隔的文本檔案，這些文本檔案可用於DataWarehouse載入常式、審計機構或其他目標。

>[!NOTE]
>
>要使導出器正常工作，日誌源必須滿足「日誌處理配置檔案」的「日誌源」 [部分中](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea)[討論的相應要求](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。

**要定義導出器，請執行以下操作：**

1. 在資料 [!DNL Transform.cfg] 工作台中開啟。 請參 [閱編輯Insight Transform.cfg檔案](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13)。
1. 按一下滑鼠右 **[!UICONTROL Exporters]**&#x200B;鍵，然後按一下 **[!UICONTROL Add New]**。
1. 選擇下列選項之一：

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**
   >[!NOTE]
   >
   >對於 [!DNL ExportVSLFile] 該選項，輸入檔案中的所有擴展欄位和表單cs(標頭&#x200B;**)的所有用戶定義欄位都始終寫入VSL輸出檔案。 如果覆寫現有的擴充欄位，新值會寫入輸出檔案，即使欄位空白亦然。

1. 使用下表作為指南編輯配置檔案中的Exportors參數：

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 參數 </th> 
      <th colname="col2" class="entry"> 說明 </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> 資料格式 </td> 
      <td colname="col2"> <p>僅限 <span class="wintitle"> 於ExportTextFile</span> 。 每個輸出行的格式，由欄位名轉義(表示為%<i>fieldname</i>%)和任何其它需要的固定文本組成。 格式應包含行分隔符，通常為[CR] [LF]。 </p> <p> 常值百分比符號(%)可透過逸出字元嵌入格式字串，如下所示：%% </p> <p> 「資料格式」參數的項目範例為 <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 欄位 </td> 
      <td colname="col2">僅限 <span class="wintitle"> 於ExportDelimitedTextFile</span> 。 要輸出的欄位的名稱。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 分隔字元 </td> 
      <td colname="col2"> <p>選填。僅限 <span class="wintitle"> 於ExportDelimitedTextFile</span> 。 用於分隔輸出檔案中欄位的字元。 </p> <p> 軟體無法轉義包含在資料值中的分隔字元。 因此，Adobe不建議使用逗號做為分隔字元。 </p> <p> 如果按住Ctrl鍵並在分隔字元參數內按一下滑鼠右鍵，則會出現「插入 <span class="wintitle"> 」功能表</span> 。 此功能表包含常用作分隔字元的特殊字元清單。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 行分隔符 </td> 
      <td colname="col2">選填。僅限 <span class="wintitle"> 於ExportDelimitedTextFile</span> 。 用於在輸出檔案中分隔行的字元。 預設值為[CR] [LF]。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 名稱 </td> 
      <td colname="col2"> <p>選填。導出器的標識符。 此名稱會出現在「詳細狀 <span class="wintitle"> 態」介面中</span> 。 </p> <p> 如需詳細狀態介面 <span class="wintitle"> 的詳細資訊</span> ，請參閱資 <i>料工作台使用指南</i>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 意見 </td> 
      <td colname="col2"> 選填。關於出口商的說明。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 輸出路徑 </td> 
      <td colname="col2"> <p>儲存輸出檔案的路徑。 路徑是相對於資料工作台伺服器安裝資料夾的。 </p> <p> <p>注意：儲存輸出資料的資料工作台伺服器是處理伺服器#0，位於 <span class="filepath"> profile.cfg檔案中</span> 。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 檔案旋轉期間 </td> 
      <td colname="col2"> <p>選填。將資料導出到輸出檔案的頻率。 每個輸出檔案都包含與稱為旋轉週期的特定時間段相關的資料。 所有時間的計算都以GMT為單位：一天從格林尼治時間的午夜開始，第二天從格林尼治時間的午夜結束，即使寫入檔案的資料包含已轉換為當地時間的欄位。 </p> <p> 可用值如下： </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> 年。 每個檔案包含一個日曆年的資料。 </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> 月。 每個檔案包含一個日曆月的資料。 月數為1（1月）至12（12月）。 </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> 一週。 每個檔案包含一週的資料。 一週從星期一開始。 開始於一年中前7天之一的周是第1週，而前（部分）周（如果有的話）是第0週。 </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> 日。 每個檔案都包含一個日曆日的資料。 </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> 一小時。 每個檔案包含一小時的資料。 </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE. 不執行任何旋轉。 所有資料都會寫入相同的檔案（或由其他參數設定所決定的一組檔案）。 請參閱 <span class="wintitle"> 此表中的「檔案名格式</span> 」參數。 </li> 
      </ul> <p>預設的檔案旋轉期間為DAY。 </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> 僅在離線模式下工作時，將檔案旋轉設定為 <span class="wintitle"> NONE</span>。 請參閱「離 <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"> 線模式</a> 」參數說明。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 檔案名格式 </td> 
      <td colname="col2"> <p>選填。輸出檔案名的格式。 </p> <p> 每個日誌條目都可以儲存在一個檔案中，其名稱是從旋轉週期的開始時間派生的，也可以從包含的行中的欄位值導出的。 檔案名中要使用的欄位被嵌入為欄位名轉義(表示為%<i>fieldname</i>%)。 </p> <p>與旋轉週期相關的檔案名元件使用下列轉義序列嵌入格式字串中： 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy%（四位數的年） </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy%（兩位數年份） </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm%（兩位數的月份，01 - 12） </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww%（兩位數的周，01 - 52） </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd%（兩位數，01 - 31） </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH%（兩位數小時，00 - 23） </li> 
      </ul> </p> <p> 預設檔案名格式 <span class="filepath"> 為%yyyy%%mm%%dd%-%x-mask%。txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> 逸出序列區分大小寫。 </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> 當「檔案旋轉期間」(File Rotation Period)設定為NONE時，每個轉義序列都會替換空字串（如果存在）。 </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> 如果「檔案名格式 <span class="wintitle"></span> 」未導致每個旋轉週期的檔案名唯一，則會生成錯誤（請參見此表中的「檔案旋轉週期」參數）。 例如，使用DAY旋轉期間時，%dd%、%mm%和%yy%或%yyy%轉義序列必須出現在模式中，以避免資料遺失。 </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> 如果您在模式中使用欄位名稱轉義序列，且給定欄位具有許多不同的值，則會為每個旋轉週期寫入許多輸出檔案。 請注意，此情況可能會導致效能不佳，因此您應謹慎使用此功能。 </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> 所有時間的計算都以GMT為單位。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 在變換時執行 </td> 
      <td colname="col2"> <p>選填。完成每個檔案後，可以執行外部(Windows)命令。 命令行由最終檔案名派生，方法是將以下轉義序列替換為此參數： </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%。 最終檔案名的目錄部分，包括尾隨反斜線。 </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%。 最終檔案的檔案名（不包括目錄和副檔名）。 </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%。 擴充功能（包括前導"。"）最終檔案名。 </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %路徑%. 檔案的完整路徑名，相當於%dir%%file%%ext%。 </li> 
      </ul> <p> 預設情況下，此參數為空（不執行任何命令）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 記憶體限制 </td> 
      <td colname="col2"> <p>選填。用於緩衝導出器輸出的記憶體量（以位元組為單位）。 預設值為10,000,000位元組。 </p> <p> <p>注意： 如果同時開啟了多個輸出檔案，則可能希望增加此值，但可能會減少系統其它元件可用的記憶體量。 但是，降低此值可能會減緩匯出程式。 如需協助，請聯絡Adobe。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 開啟檔案限制 </td> 
      <td colname="col2"> <p>選填。可同時開啟以從導出器輸出的最大檔案數。 如果超出此數目，事件記錄中會記錄錯誤，而資料工作台伺服器會停止執行。 預設值為 1000。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 在檔案中定義匯出器（並變更其他參數）後，請將檔案儲存在本機 [!DNL Transform.cfg] ，並儲存至資料工作台伺服器機器上的適當描述檔。
