---
description: 如果您使用從網站流量收集到的資料，則可使用「作業化」轉換來決定如何定義作業。
solution: Analytics
title: 作業化
topic: Data workbench
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 作業化{#sessionize}

如果您使用從網站流量收集到的資料，則可使用「作業化」轉換來決定如何定義作業。

轉換會以時間戳記和追蹤ID作為輸入，並輸出每個記錄項目的作業編號。 具有指定追蹤ID的第一個工作階段的工作階段編號為&quot;1&quot;，具有相同追蹤ID的第二個工作階段的工作階段編號為&quot;2&quot;，依此類推。 輸出可直接用作作業鍵，因為每個作業都有唯一值。

>[!NOTE]
>
>若要運作，轉 [!DNL Sessionize] 換需要資料按時間排序，並依來源資料中的追蹤ID分組。 因此， [!DNL Sessionize] 只有在檔案或檔案中 [!DNL Transformation.cfg] 定義時才可 [!DNL Transformation Dataset Include] 用。

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
   <th colname="col3" class="entry"> 預設值 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 轉換的描述性名稱。 您可以在此輸入任何名稱。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 意見 </td> 
   <td colname="col2"> 選填。關於轉變的附註。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 條件 </td> 
   <td colname="col2"> 應用此轉換的條件。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入時間戳記 </td> 
   <td colname="col2"> 包含要使用的時間戳記值的欄位。 </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸入追蹤ID </td> 
   <td colname="col2"> <p>包含要使用的追蹤ID值的欄位。 值必須是64位（16位）或更小的十六進位數字，或16位或更小的十進位整數。 </p> <p> <p>注意：如果您想要使用x-trackingid以外的欄位作為追蹤ID，您必須先對欄位進行雜湊。 請參閱 <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> 雜湊</a>。 </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>最大會話持續時間 </p> </td> 
   <td colname="col2">啟動新會話前的會話最長長度。 （這可讓具有自動內容重新整理功能的網頁，不會建立任意長度的工作階段）。如果滿 <span class="wintitle"> 足「逾時條件</span> 」，且點按的反向連結設定為「內部網域」參數中的其中一個項目，則會使用「最大作業持續時間」來定義作業結束。 不論會話包含多少次點按，都不得超過指定的「最大會話持續時間」。 建議值為48小時。 如需「最大作業持續時間」和「內部網域」參數的詳細資訊，請參 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> 閱「Web資料的組態設定」</a>。 </td> 
   <td colname="col3"> 48 小時 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 輸出會話編號 </td> 
   <td colname="col2"> 儲存會話編號的欄位。 此欄位對每個訪客的每個作業都有唯一的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 工作階段逾時 </td> 
   <td colname="col2"> <p>在指定訪客的記錄項目之間需要傳遞的時間量，以決定一個作業結束和新作業開始的時間（即用來定義使用者作業的典型逾時）。 此參數的建議值為30分鐘。 如果「逾時條件」未滿足，且點按的反向連結未設定為「內部網域」參數中的其中一個反向連結，則會使用「作業逾時」來定義作業。 </p> <p> 如果滿足「逾時條件」，且記錄項目的cs（反向連結網域）位於內部網域清單中，則「最大作業持續時間」會決定目前記錄項目是現有作業的一部分，還是新作業的開始。 </p> <p> 如需「作業逾時」參數的詳細資訊，請參閱「 <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Web資料的組態設定」</a>。 </p> </td> 
   <td colname="col3"> 30 分鐘 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 逾時條件 </td> 
   <td colname="col2"> 必須滿足的條件，才能將日誌條目視為新會話的開始。 請注意，日誌條目和上一個日誌條目之間所經過的時間量至少必須是「會話超時」參數的值。 </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

發生以下任一情況時，就會開始新會話：

* 追蹤ID會變更。
* 自最後一個日誌條目起的時間至少等於「會話超時」參數的值，並且滿足「超時條件」。
* 自上次會話的第一個日誌條目開始的時間超過「最大會話持續時間」參數的值。

>[!NOTE]
>
>如果已將「最大會話持續時間」和「會話超時」定義為 [!DNL Session Parameters.cfg] 檔案中的參數，請不要在配置中為它們輸入值。 您可以輸入 *$（參數名稱）* ，如以下範例所示。 如需這些參數的詳細資訊，請參 [閱Web資料的組態設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

此 [!DNL Sessionize] 示例中的轉換將作為其輸入x-timestamp和x-trackingid欄位，並在x-session-key欄位中記錄每個日誌條目的會話編號。 這種轉變 [!DNL Timeout Condition] 基於一個條 [!DNL Neither] 件：如果記錄項目的cs(referrer-domain)欄位符合「內部網域」參數的成員，則條件會評估為false。 請注意對「內部網域」和「作業逾時」參數的參考。

有關的資訊，請 [!DNL NeitherCondition]參閱 [條件](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。 如需內部網域和作業逾時參數的詳細資訊，請參 [閱Web資料的組態設定](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)。

![](assets/cfg_TransformationType_Sessionize.png)

