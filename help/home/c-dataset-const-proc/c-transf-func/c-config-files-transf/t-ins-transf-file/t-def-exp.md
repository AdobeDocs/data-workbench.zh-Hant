---
description: 導出器提供用於輸出事件資料的指令。
title: 定義匯出工具
uuid: 565d4482-6c25-407c-bda7-0d116180902a
exl-id: 5de6266a-e959-414c-9512-5e9f4011881b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 2%

---

# 定義匯出工具{#defining-exporters}

{{eol}}

導出器提供用於輸出事件資料的指令。

轉換功能提供三種匯出類型 [!DNL .vsl] 檔案、日誌檔案、XML檔案和ODBC資料作為 [!DNL .vsl] 檔案、文本檔案或分隔文本檔案，這些檔案可用於DataWarehouse載入常式、審計機構或其他目標。

>[!NOTE]
>
>要使導出器正常工作，日誌源必須滿足 [記錄來源](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) 區段 [記錄處理組態檔](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

**要定義導出器，請執行以下操作**

1. 開啟 [!DNL Transform.cfg] 在data workbench中。 請參閱 [若要編輯Insight Transform.cfg檔案](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13).
1. 按一下右鍵 **[!UICONTROL Exporters]**，然後按一下 **[!UICONTROL Add New]**.
1. 選取下列其中一個選項：

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**

   >[!NOTE]
   >
   >若 [!DNL ExportVSLFile] 選項，輸入檔案中的所有擴展欄位以及窗體cs(*標題*)一律寫入VSL輸出檔案。 如果覆蓋現有的擴展欄位，則新值將寫入輸出檔案，即使該欄位為空。

1. 使用下表作為指南，編輯配置檔案中的導出器參數：

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
      <td colname="col2"> <p>針對 <span class="wintitle"> ExportTextFile</span> 只有。 每個輸出行的格式，由欄位名稱逸出（以%表示）組成<i>fieldname</i>%)和任何其他需要的固定文字。 格式應包含行分隔符，通常為[CR] [LF]。 </p> <p> 文字百分比符號(%)可借由逸出字元嵌入格式字串，如下所示：% </p> <p> 資料格式參數的項目範例為 <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 欄位 </td> 
      <td colname="col2">針對 <span class="wintitle"> ExportDelimetedTextFile</span> 只有。 要輸出的欄位名稱。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 分隔字元 </td> 
      <td colname="col2"> <p>選填。針對 <span class="wintitle"> ExportDelimetedTextFile</span> 只有。 用於分隔輸出檔案中欄位的字元。 </p> <p> 軟體無法逸出資料值中包含的分隔字元。 因此，Adobe不建議將逗號當作分隔字元。 </p> <p> 按住Ctrl鍵並在「分隔字元」參數內按一下滑鼠右鍵， <span class="wintitle"> 插入</span> 中。 此菜單包含通常用作分隔符的特殊字元的清單。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 行分隔符 </td> 
      <td colname="col2">選填。針對 <span class="wintitle"> ExportDelimetedTextFile</span> 只有。 用於在輸出檔案中分隔行的字元。 預設值為[CR] [LF]。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 名稱 </td> 
      <td colname="col2"> <p>選填。導出器的標識符。 此名稱會顯示在 <span class="wintitle"> 詳細狀態</span> 介面。 </p> <p> 如需 <span class="wintitle"> 詳細狀態</span> 介面，請參閱 <i>Data Workbench使用手冊</i>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 註解 </td> 
      <td colname="col2"> 選填。關於出口商的筆記。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 輸出路徑 </td> 
      <td colname="col2"> <p>儲存輸出檔案的路徑。 路徑相對於Data Workbench伺服器安裝資料夾。 </p> <p> <p>注意：儲存輸出資料的Data Workbench伺服器，是處理#0中的伺服器 <span class="filepath"> profile.cfg</span> 檔案。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 檔案旋轉期間 </td> 
      <td colname="col2"> <p>選填。將資料導出到輸出檔案的頻率。 每個輸出檔案都包含與稱為旋轉週期的特定時段相關的資料。 所有時間的計算都以GMT為單位：某一天從格林尼治時間的午夜開始，第二天從格林尼治時間的午夜結束，即使寫入檔案的資料包含已轉換為當地時間的欄位亦然。 </p> <p> 可用值如下： </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> 年。 每個檔案包含一個日曆年的資料。 </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> 月。 每個檔案包含一個日曆月的資料。 月份編號為1（1月）至12（12月）。 </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> 周。 每個檔案包含一週的資料。 星期一開始。 從一年中前七天之一開始的周是第1週，而前（部分）周（如果有的話）是第0週。 </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> 日。 每個檔案包含一個日曆日的資料。 </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> 小時。 每個檔案包含1小時的資料。 </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE. 不執行旋轉。 所有資料都會寫入相同的檔案（或由其他參數設定所決定的一組檔案）。 請參閱 <span class="wintitle"> 檔案名格式</span> 參數。 </li> 
      </ul> <p>預設檔案旋轉週期為DAY。 </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> 僅當在中工作時，才將檔案旋轉設定為NONE <span class="wintitle"> 離線模式</span>. 請參閱 <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"> 離線模式</a> 參數說明。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 檔案名格式 </td> 
      <td colname="col2"> <p>選填。輸出檔案名的格式。 </p> <p> 每個日誌條目都可以儲存在一個檔案中，該檔案的名稱是從旋轉週期的開始時間派生的，也可以從包含的行中的欄位值派生的。 檔案名中要使用的欄位被嵌入為欄位名稱逸出（以%表示）<i>fieldname</i>%)。 </p> <p>與旋轉週期相關的檔案名元件使用以下轉義序列嵌入到格式字串中： 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy%（四位數年） </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy%（兩位數年份） </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm%（兩位數月，01 - 12） </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww%（兩位數的周，01 - 52） </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd%（兩位數，01 - 31） </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH%（兩位數小時，00 - 23） </li> 
      </ul> </p> <p> 預設檔案名格式為 <span class="filepath"> %yyyy%%mm%%dd%-%x-mask%。txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> 逸出序列區分大小寫。 </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> 當「檔案旋轉週期」設定為「無」時，每個轉義序列都會替換空字串（如果存在）。 </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> 若 <span class="wintitle"> 檔案名格式</span> 不會導致每個旋轉週期的檔案名唯一（請參見此表中的「檔案旋轉週期」參數）。 例如，使用DAY旋轉期間時，%dd%、%mm%和%yy%或%yyyy%轉義序列必須以模式存在，以避免資料丟失。 </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> 如果您在模式內使用欄位名稱逸出序列，且指定的欄位有許多不同的值，則會為每個旋轉期間寫入許多輸出檔案。 請注意，此情境可能會導致效能不佳，因此您應謹慎使用此功能。 </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> 所有時間的計算都以GMT為單位。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 在變換時執行 </td> 
      <td colname="col2"> <p>選填。每個檔案完成後，可執行外部(Windows)命令。 命令行從最終檔案名派生，方法是將以下轉義序列替換為此參數： </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%。 最終檔案名的目錄部分，包括尾端反斜線。 </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%。 最終檔案的檔案名（不包括目錄和副檔名）。 </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%。 擴充功能（包括前導「。」） 檔案名的。 </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %路徑%. 檔案的完整路徑名，等同於%dir%file%%ext%。 </li> 
      </ul> <p> 預設情況下，此參數為空（不執行任何命令）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 記憶體限制 </td> 
      <td colname="col2"> <p>選填。用於緩衝導出器輸出的記憶體量（以位元組為單位）。 預設值為10,000,000位元組。 </p> <p> <p>注意：如果您有多個同時開啟的輸出檔案，則可能希望增加此值，但您可能會減少系統其他元件可用的記憶體量。 但是，降低此值可能會減緩匯出程式。 如需協助，請聯絡Adobe。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 開啟檔案限制 </td> 
      <td colname="col2"> <p>選填。可同時開啟以從導出器輸出的最大檔案數。 如果超過此數目，事件記錄中會記錄錯誤，且Data Workbench伺服器會停止執行。 預設值為 1000。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 在定義導出器後（並對其他參數進行更改）, [!DNL Transform.cfg] 檔案，將檔案儲存在本機，然後儲存至data workbench伺服器電腦上的適當設定檔。
