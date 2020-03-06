---
description: 本節說明如何建立資料工作台資料集的時間戳記。
title: 設定事件時間
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定事件時間{#setting-up-event-time}

本節說明如何建立資料工作台資料集的時間戳記。

## 瞭解事件時間 {#section-e10ef2b5b6244dc5b215836e3c77d663}

事件時間是請求（或事件）發生的日期和時間。

通常，對於線上資料， *x_hit_time_gmt* 會用作時間戳記欄位。 呼叫的時間可用作離線資料的時間戳記（例如呼叫中心資料）。 這是必填欄位，所有資料來源都應有一個欄位，可當做時間戳記使用。 此資訊應由貴組織提供。

在DWB中，下列預先定義的變數會擷取時間戳記：

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> 伺服器收到請求的日期和時間(GMT)。 時間以1600年1月1日以來的100納秒數表示。 </p> <p>範例：127710989320000000是2005年9月13日星期二11:28:52.000000的 <i>x-timestamp</i> 值。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> ，格式為YYYY-MM-DD HH:MM:SS.mm。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> 是代表自1970年1月1日00:00:01以來的秒數的epoc時間。 </td> 
  </tr> 
 </tbody> 
</table>

根據日期欄位的格式，會使用x-timestamp或x-unixtime或x-timestring。 例如，如果傳入資料的格式為YYYY-MM-DD，則會使用x-timestring。

時間戳以其中一種格式定義，DWB內部產生其他兩種格式。 此外，這些是預先定義的DWB欄位，不應將相同名稱用於任何其他欄位。

## DWB中定義的時區 {#section-3cdd12254342442b917376661e1d9c9f}

如果日期欄位包含下列任一時區，DWB會考慮該特定時區的整列。 例如，一個檔案的日期定義為2015-01-01 00:00:00 gmt，而另一個檔案的值定義為2015-01-01 00:00:00 cst，則第一個檔案的日期會被視為GMT時區，而第二個檔案的日期則是CST時區。

| 程式碼 | 時區 |
|---|---|
| gmt | 格林威治標準時間 |
| est | Eastern Standard |
| edt | 東日光 |
| cst | Central Standard |
| cdt | 中央日光 |
| mst | Mountain Standard |
| mdt | 山地日光 |
| pst | Pacific Standard |
| pdt | 太平洋日光 |

>[!NOTE]
>
>DWB僅處理上述時區。

## 設定自訂時區 {#section-7c351921f22b439b81c73f40d5b47536}

DWB不處理時區中的偏移。 要考慮時區中的偏移，應在該偏移時區中格式化資料。

範例：若要考慮CST時區的日期格式，資料應使用用戶端的YYYY-MM-DD HH:MM:SS UTC +/-HHMM格式。

世界協調時2015-10-18 05:00:00

## 如何設定事件時間／時間戳記 {#section-81507080f0b44ae6b83d3650ba019812}

根據日期欄位格式， *使用x-timestamp、x-unixtime**或x-timestring* 變數。 在下列範例中，由於 *x-hit_time_gmt* 為unix epoc格式，因此會 *使用x-unixtime* 。

在DWB檔案( [!DNL foundation.cfg] 或「資料集記錄處理」資料夾下的任何其他設定檔案)中，使用「複製」轉換來設定「事件時間」，如下所示：

根據日期欄位格式，會使用x-timestamp、x-unixtime或x-timestring變數。 在下列範例中，由於x-hit_time_gmt為unix epoc格式，因此會使用x-unixtime。

在insight foundation.cfg（或Datasetà log processing資料夾下的任何其他設定）中，使用「複製」轉換來設定「事件時間」，如下所示： ![](assets/dwb_impl_timestamp1.png)

如果日期為YYYY-MM-DD HH:MM:SS.mmm格式，則使用x-timestring。 ![](assets/dwb_impl_timestamp2.png)範例：如果日期欄位的格式不是在DWB中定義的YYYY/MM/DD，則首先以DWB所接受的時間戳記格式之一格式設定日期欄位，然後將其指派給對應的變數。 在下方的螢幕擷取中，日期會先轉換為YYYY-MM-DD格式，然後指派給*x-timestring *variable。 ![](assets/dwb_impl_timestamp3.png)

