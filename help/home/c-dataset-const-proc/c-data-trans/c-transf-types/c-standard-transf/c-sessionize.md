---
description: 如果您使用從網站流量收集的資料，可使用Sessionize轉換來判斷如何定義工作階段。
title: Sessionize
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
exl-id: bb25cb4b-7185-4524-8ff5-740b672e1cd9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Sessionize{#sessionize}

{{eol}}

如果您使用從網站流量收集的資料，可使用Sessionize轉換來判斷如何定義工作階段。

轉換會以時間戳記和追蹤ID作為輸入，並輸出每個記錄項目的工作階段號碼。 具有指定追蹤ID的第一個工作階段的工作階段編號為「1」，具有相同追蹤ID的第二個工作階段則為「2」，以此類推。 輸出可以直接用作會話密鑰，因為每個會話都有唯一值。

>[!NOTE]
>
>若要運作， [!DNL Sessionize] 轉換需要資料按時間排序，並依來源資料中的追蹤ID分組。 因此， [!DNL Sessionize] 只有在 [!DNL Transformation.cfg] 檔案或 [!DNL Transformation Dataset Include] 檔案。

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 註解 </td> 
   <td colname="col2"> 選填。轉換的相關附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 套用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入時間戳記 </td> 
   <td colname="col2"> 包含要使用的時間戳記值的欄位。 </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入追蹤ID </td> 
   <td colname="col2"> <p>包含要使用的追蹤ID值的欄位。 值必須是64位（16位）或更小的十六進位數字，或16位或更小的十進位整數。 </p> <p> <p>注意：如果您想要將x-trackingid以外的欄位用於追蹤ID，則需要先雜湊欄位。 請參閱 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> 雜湊</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最大會話持續時間 </p> </td> 
   <td colname="col2">新會話開始前最長的會話長度。 （這可讓具有自動內容重新整理的網頁不會建立任意長度的工作階段。） 若 <span class="wintitle"> 逾時條件</span> 會得到滿足，且點按的反向連結會設為「內部網域」參數中的其中一個項目，則「最大工作階段持續時間」會用來定義工作階段的結尾。 不論包含多少點按，任何工作階段都不得超過指定的最大工作階段持續時間。 建議值為48小時。 如需「最大工作階段期間」和「內部網域」參數的詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Web資料的組態設定</a>. </td> 
   <td colname="col3"> 48 小時 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出會話數 </td> 
   <td colname="col2"> 儲存會話號的欄位。 此欄位對每個訪客的每個工作階段都有不重複的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段逾時 </td> 
   <td colname="col2"> <p>在指定訪客的記錄項目之間需要傳遞的時間量，以判斷一個工作階段的結尾和新工作階段的開始（即用來定義使用者工作階段的一般逾時）。 此參數的建議值為30分鐘。 如果不符合逾時條件，且點按的反向連結未設為內部網域參數中的其中一個反向連結，則會使用「工作階段逾時」來定義工作階段。 </p> <p> 如果滿足逾時條件，且記錄項目的cs(referrer-domain)位於內部網域清單中，則「最大工作階段持續時間」會判斷目前記錄項目是現有工作階段的一部分，還是新工作階段的開始。 </p> <p> 如需工作階段逾時參數的詳細資訊，請參閱 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Web資料的組態設定</a>. </p> </td> 
   <td colname="col3"> 30 分鐘 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 逾時條件 </td> 
   <td colname="col2"> 必須滿足的條件，才能將記錄項目視為新工作階段的開始。 請注意，在日誌條目和前一個日誌條目之間經過的時間量必須至少是Session Timeout參數的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

發生下列任一情況時，就會開始新的工作階段：

* 追蹤ID會變更。
* 自上次記錄項目以來的時間至少等於Session Timeout參數的值，並且滿足Timeout條件。
* 自上次會話的第一個日誌條目以來的時間超過了Maximum Session Duration參數的值。

>[!NOTE]
>
>如果您已將「最大工作階段持續時間」和「工作階段逾時」定義為 [!DNL Session Parameters.cfg] 檔案中，請勿在設定中輸入其值。 您可以輸入 *$（參數名稱）* 如下列範例所示。 如需這些參數的詳細資訊，請參閱 [Web資料的組態設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

此 [!DNL Sessionize] 此範例中的轉換會以x-timestamp和x-trackingid欄位作為輸入，並在x-session-key欄位中記錄每個記錄項目的工作階段號碼。 轉型 [!DNL Timeout Condition] 根據 [!DNL Neither] 條件：如果記錄項目的cs(referrer-domain)欄位符合Internal Domains參數的成員，則條件會評估為false。 請注意對內部網域和工作階段逾時參數的參考。

如需 [!DNL NeitherCondition]，請參閱 [條件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). 如需內部網域和工作階段逾時參數的相關資訊，請參閱 [Web資料的組態設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

![](assets/cfg_TransformationType_Sessionize.png)
