---
description: 您可以建立任何可計數維度的元素區段，然後以批次或持續即時方式將該區段的資料輸出至以Tab分隔的檔案。
solution: Analytics
title: 設定要匯出的區段
topic: Data workbench
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定要匯出的區段{#configure-segments-for-export}

您可以建立任何可計數維度的元素區段，然後以批次或持續即時方式將該區段的資料輸出至以Tab分隔的檔案。

每當您匯出區段時，即會輸出該區段中所有維度元素的量度或維度資料。您可以控制輸出資料的格式化方式，以方便其他系統載入資料。

>[!NOTE]
>
>您無法匯出報表維度，因為它們使用 [!DNL report time.metric] 檔案做為參考。 因應措施是，如果您在描述檔中置入 [!DNL report time.metric] 硬式編碼，區段匯出就可將其用作報告維度的參考點。 不過， [!DNL report time.metric] 不會根據描述檔的「截止時間」自動更新，因此當您要變更報告維度參照時，必須變更硬式編碼檔 [!DNL report time.metric] 案。

若要設定要匯出的區段，您必須開啟並編輯檔 [!DNL .export] 案。

1. 在中， [!DNL Profile Manager]按一下列 **[!UICONTROL Export]** 中的目 [!DNL File] 錄以顯示其內容。

       如果「導出」目錄不存在，請按如下方式建立該目錄：
   
   1. 導覽至您的資料工作台安裝目錄。
   1. 開啟您正在使用的配置檔案的目錄。
   1. 在「描述檔」目錄中，建立名為「匯出」的新目錄。

1. 在「導 [!DNL Profile Manager]出」目錄的欄中，以滑鼠右鍵按一下空白 [!DNL User] 儲存格，然後按一下 **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**。

   名為的檔案 [!DNL New Segment Export.export] 將出現在「導 [!DNL File] 出」的列中。

1. 在檔案的列中按一下右鍵，並在「文 [!DNL User] 件」參數中鍵入新名稱，以更名新檔案。
1. 在檔案的欄中按一下滑鼠右鍵，然後按一 [!DNL User] 下>以開啟新檔案 **[!UICONTROL Open]****[!UICONTROL from the workbench]**。

   此時將出現檔案的 [!DNL .export] 配置窗口。

1. 按一 **[!UICONTROL Query]**&#x200B;下，然後修改檔案的欄 [!DNL .export] 位，如下表所述：

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 對於此參數…… </th> 
   <th colname="col2" class="entry"> 提供此資訊…… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 命令 </td> 
   <td colname="col2"> <p>選填。建立輸出檔案後要執行的程式。 此欄位必須引用執行檔( <span class="filepath"> .exe </span> 檔案)，而不是shell命令。 </p> <p>注意： 如果命令參數中有空格，則段導出將失敗。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 篩選 </td> 
   <td colname="col2"> <p>選填。命名篩選或篩選運算式。 您可以使用篩選編輯器建立命名篩選器，然後在此處輸入該篩選器的名稱，或者輸入篩選器運算式本身。 </p> <p>如需篩選編輯器的詳細資訊，請參閱 <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> 篩選編輯器 </a>。 如需篩選運算式語法的詳細資訊，請參 <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> 閱篩選運算式的語法 </a>。 </p> <p>與篩選器匹配的級別元素將導出，而所有其他元素則不導出。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 層級 </td> 
   <td colname="col2"> <p>要導出其元素的可計數維。 </p> <p>範例：「訪客」層級會匯出每位訪客的一列資料。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出檔案 </td> 
   <td colname="col2"> <p>導出資料的路徑和檔案名。 如果描述檔在資料工作台伺服器叢集上執行，每個資料工作台伺服器都會寫入包含部分資料的輸出檔案。 </p> <p>資料工作台伺服器安裝目錄包含匯出目錄，您可在此儲存輸出檔案。 例如，您可以輸入 <span class="filepath"> Exports\Visitor Segment.txt </span>，其中 <span class="filepath"></span> Visitor Segment.txt是包含已匯出資料的檔案名稱。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出格式 </td> 
   <td colname="col2"> 要針對每個「層級」元素匯出的量度或維度資料。 如果輸出是Tab分隔的檔案，則欄位應以Tab字元分隔，格式應以適當的新行字元結尾。 如需詳細資訊，請參 <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> 閱關於輸出格式 </a>。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 排程結束時間 </td> 
   <td colname="col2"> <p>選填。排程的結束日期和時間，包括時區。 </p> <p>格式：YYYY-MM-DD hh:mm時區 </p> <p>範例：2013-08-01 12:01東部夏令時間 </p> <p>排程的匯出目前停止；但是，「輸出檔案」(Output File)在其定義被更改時仍會再生。 若未定義「排程間隔」，此欄位就毫無意義。 如需時區設定的詳細資訊，請參閱資料集 <i>設定指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 排程間隔 </td> 
   <td colname="col2"> 選填。再生輸出檔案的頻率。 支援的值包括小時、日、周和月。 「輸出檔案」(Output File)在其定義隨時更改時仍會再生。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 排程開始時間 </td> 
   <td colname="col2"> <p>選填。計畫的開始日期和時間，包括時區。 </p> <p>格式：YYYY-MM-DD hh:mm時區 </p> <p>範例：2013-08-01 12:01東部夏令時間 </p> <p>排程匯出目前會開始，而排程是與此時相對的。 若未定義「排程間隔」，此欄位 <span class="wintitle"> 就毫無意義 </span>。 如需時區設定的詳細資訊，請參閱資料集 <i>設定指南</i>。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 時間限制（秒） </td> 
   <td colname="col2"> 選填。產生區段匯出時允許的最長時間。 如果超出指定的間隔，則導出將重新開始。 將此值設為0（零）會移除限制。 預設值為600秒。 </td> 
  </tr> 
 </tbody> 
</table>

1. 在視窗頂 **[!UICONTROL (New)]** 端按一下滑鼠右鍵，然後按一下 **[!UICONTROL Save]**。
1. 要使此檔案對工作配置檔案的所有用戶都可用，請按一下右鍵列中已建立 [!DNL .export] 檔案的複選 [!DNL User] 標籤，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*。

   >[!NOTE]
   >
   >將檔 [!DNL .export] 案儲存至資料工作台伺服器會立即執行一次匯出，即使「排程開始時間」設定為未來日期和時間亦然。

   The following is a sample [!DNL .export] file.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >範例 [!DNL Visitor Segment.export] 中顯示的檔案會參照「訪客區段」篩選。 修改此篩選器的定義會更改導出的定義。

