---
description: 本節說明如何建立Data Workbench資料集的時間戳記。
title: 設定事件時間
uuid: 0230154d-05a2-44cf-9456-0a27e55f58ef
exl-id: 9632e713-5cf9-4acf-aafa-bfdf79a51ad9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---

# 設定事件時間{#setting-up-event-time}

{{eol}}

本節說明如何建立Data Workbench資料集的時間戳記。

## 了解事件時間 {#section-e10ef2b5b6244dc5b215836e3c77d663}

事件時間是請求（或事件）發生的日期和時間。

通常，對於線上資料， *x_hit_time_gmt* 用作時間戳欄位。 呼叫的時間可作為離線資料（例如客服中心資料）的時間戳記。 這是必填欄位，所有資料來源中應包含一個欄位，可作為時間戳記使用。 此資訊應由貴組織提供。

在DWB中，下列預先定義的變數會擷取時間戳記：

<table id="table_C24BD56CEB4E42F68D645EBB65585D16"> 
 <tbody> 
  <tr> 
   <td colname="col1"><i>x-timestamp</i> </td> 
   <td colname="col2"> <p> 伺服器收到請求的日期和時間(GMT)。 時間以1600年1月1日以來的100納秒數表示。 </p> <p>範例：127710989320000000是 <i>x-timestamp</i> 11的值:28:52.0000000 2005年9月13日星期二。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-timestring</i> </td> 
   <td colname="col2"> <i>x-timestamp</i> 格式為YYYY-MM-DD HH:MM:嗯。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"><i>x-unixtime</i> </td> 
   <td colname="col2"> <i>x-unixtime</i> 是epoc時間，代表自1970年1月1日起的秒數，為00:00:01. </td> 
  </tr> 
 </tbody> 
</table>

根據日期欄位的格式，會使用x-timestamp或x-unixtime或x-timestring。 例如，如果傳入資料的格式為YYYY-MM-DD，則使用x-timestring。

時間戳記以其中一種格式定義，DWB會內部產生其他兩種格式。 此外，這些是預先定義的DWB欄位，其他欄位不應使用相同名稱。

## DWB中定義的時區 {#section-3cdd12254342442b917376661e1d9c9f}

如果日期欄位包含下列任何時區，DWB會考量該特定時區的整列。 例如，一個檔案的日期定義為2015-01-01 00:00:00 gmtand另一個檔案的值為2015-01-01 00:00:00 cst，則第一個檔案的日期將以GMT時區計算，而第二個檔案的日期將以CST時區計算。

| 程式碼 | 時區 |
|---|---|
| gmt | 格林威治中值 |
| est | 東部標準 |
| edt | 東日光 |
| cst | 中央標準 |
| cdt | 中央日光 |
| mst | 山區標準 |
| mdt | 山光 |
| pst | 太平洋標準 |
| pdt | 太平洋日光 |

>[!NOTE]
>
>DWB只會處理上述時區。

## 設定自訂時區 {#section-7c351921f22b439b81c73f40d5b47536}

DWB不會處理時區中的偏移。 若要在時區中考慮偏移，資料應在該偏移時區中格式化。

範例：若要考慮CST時區的日期格式，資料應為YYYY-MM-DD HH:MM:來自用戶端的SS UTC +/-HHMM格式。

2015-10-18 05:00:世界協調時–200

## 如何設定事件時間/時間戳記 {#section-81507080f0b44ae6b83d3650ba019812}

根據日期欄位格式， *x-timestamp, x-unixtime* 或 *x-timestring* 變數。 在以下範例中，由於 *x-hit_time_gmt* 採用unix epoc格式， *x-unixtime* 中所有規則的URL區段。

在DWB中 [!DNL foundation.cfg] 檔案（或「資料集記錄處理」資料夾下的任何其他設定檔案），請使用「複製」轉換來設定「事件時間」，如下所示：

根據日期欄位格式，使用x-timestamp、x-unixtime或x-timestring變數。 在以下範例中，由於x-hit_time_gmt採用unix epoc格式，因此會使用x-unixtime。

在insight foundation.cfg（或Datasetà記錄處理資料夾下的任何其他設定）中，使用Copy轉換來設定事件時間，如下所示： ![](assets/dwb_impl_timestamp1.png)

如果日期為YYYY-MM-DD HH:MM:SS.mmm格式，使用x-timestring。 ![](assets/dwb_impl_timestamp2.png)範例：如果日期欄位的格式並非在DWB（即YYYY/MM/DD）中定義，則首先以DWB接受的時間戳記格式之一格式設定日期欄位，然後將其指派給對應的變數。 在下方螢幕擷取中，日期會先轉換為YYYY-MM-DD格式，然後指派給*x-timestring *變數。 ![](assets/dwb_impl_timestamp3.png)
