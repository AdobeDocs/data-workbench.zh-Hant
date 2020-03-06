---
description: 本節說明如何為架構設計和實施的資料工作台資料集建立主要索引鍵（追蹤ID）。
title: 資料處理——構建主鍵
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 資料處理——構建主鍵{#data-processing-building-primary-key}

本節說明如何為架構設計和實施的資料工作台資料集建立主要索引鍵（追蹤ID）。

## 瞭解追蹤ID {#section-24683031044a4af49988655ccb9a45fd}

在DWB（使用解碼器）中讀取和解碼資料後，第一步是定義追蹤ID和時間戳記。 追蹤ID是可唯一識別客戶記錄的識別碼。 它可以是動態消息中的任何欄位，例如電子郵件ID、社交安全號碼、Cookie ID等。 用作追蹤ID的欄位由用戶端在搜尋工作階段期間決定。 追蹤ID和時間戳記是必填欄位，必須針對每個記錄定義。

通常，對於線上資料，Cookie ID( *x-visid_high* 和* x-visid_low*的組合)是唯一客戶識別的預設機制，但是，這可依客戶需求而變更。 請求（或事件）發生的日期和時間是 *x-timestamp*。 DWB中的所有記錄都是依 *照trackingid分組* ，並在時間戳記上排序。 「必要欄位」 [!DNL Definitions.cfg] 檔案是「記錄處理資料集包含」檔案，定義必要欄位： *x-trackingid* 和 *x-timestamp*。

注意：*x-trackingid *在DWB中是內建欄位，此名稱不應用於任何其他欄位。

**範例1**:使用 *Cookie ID建立* x-trackingid（僅使用線上資料時）

若要使用Cookie ID在DWB中建立*x-trackingid *，請使用Hash函式在檔案中建立 *x-trackingid* (在中定義追蹤ID是最佳實務，但可在資料夾下的任何其他設定檔案中定義 [!DNL foundation.cfg][!DNL foundation.cfg][!DNL Dataset > log processing] )，如下所示：

![](assets/dwb_impl_primary_key1.png)

**範例2**:使用 *電子郵件ID* （當有線上和離線資料時）建立x-trackingid

假設離線和線上資料皆可使用（在此範例中），而且資料來源中都提供電子郵件ID。 由於電子郵件ID可唯一識別客戶，因此將用來建立 *x-trackingid*。

使用雜湊函式建立 *trackingId* ，如所示：

![](assets/dwb_impl_primary_key2.png)

