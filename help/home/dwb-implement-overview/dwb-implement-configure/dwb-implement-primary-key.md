---
description: 本節說明如何為Data Workbench資料集建立主要索引鍵（追蹤ID），以進行結構設計和實作。
title: 資料處理 - 建立主索引鍵
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# 資料處理 - 建立主索引鍵{#data-processing-building-primary-key}

{{eol}}

本節說明如何為Data Workbench資料集建立主要索引鍵（追蹤ID），以進行結構設計和實作。

## 了解追蹤ID {#section-24683031044a4af49988655ccb9a45fd}

在DWB中讀取和解碼資料（使用解碼器）後，第一步是定義追蹤ID和時間戳記。 追蹤ID是可唯一識別客戶記錄的識別碼。 它可以是動態消息中的任何欄位，例如電子郵件ID、社會安全號碼、Cookie ID等。 用作追蹤ID的欄位由用戶端在探索工作階段期間決定。 追蹤ID和時間戳記是必填欄位，必須為每個記錄定義。

對於線上資料，通常會使用Cookie ID(組合 *x-visid_high* 和* x-visid_low*)是唯一客戶識別的預設機制，但可根據客戶的需求變更。 請求（或事件）發生的日期和時間為 *x-timestamp*. DWB中的所有記錄均按 *trackingid* 並按時間戳記排序。 必填欄位 [!DNL Definitions.cfg] 檔案是記錄處理資料集包含檔案，用於定義必要欄位： *x-trackingid* 和 *x-timestamp*.

注意：*x-trackingid *在DWB中為內建欄位，此名稱不應用於任何其他欄位。

**範例1**:建立 *x-trackingid* 使用Cookie ID（僅使用線上資料時）

若要使用Cookie ID在DWB中建立*x-trackingid *，請使用雜湊函式來建立 *x-trackingid* 在 [!DNL foundation.cfg] 檔案(在 [!DNL foundation.cfg] 但可在下列任何其他設定檔案中定義： [!DNL Dataset > log processing] 資料夾)，如下所示：

![](assets/dwb_impl_primary_key1.png)

**範例2**:建立 *x-trackingid* 使用電子郵件ID（當線上和離線資料皆可用時）

假設離線和線上資料皆可用（在此範例中），且資料來源中皆提供電子郵件ID。 由於電子郵件ID可唯一識別客戶，因此將用來建立 *x-trackingid*.

使用雜湊函式來建立 *trackingId* 如所示：

![](assets/dwb_impl_primary_key2.png)
