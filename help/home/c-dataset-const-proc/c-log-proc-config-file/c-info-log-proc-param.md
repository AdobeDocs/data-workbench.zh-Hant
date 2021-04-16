---
description: 連結至Log Processing.cfg檔案中特定參數的其他資訊。
title: 記錄處理參數
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# 記錄處理參數{#log-processing-parameters}

連結至Log Processing.cfg檔案中特定參數的其他資訊。

<!--
c_data_filters.xml
-->

## 資料篩選器 {#data-filters}

在[!DNL Log Processing.cfg]檔案中定義的篩選器包括：

* 結束時間
* 雜湊閾值
* 開始時間

由這些參數定義的過濾發生在日誌條目離開解碼器之後和轉換之後，但在[!DNL Log Entry Condition]評估它們之前。 一般而言，變更這些參數會變更資料集的組成。

建議使用[!DNL Sensor]資料來源來建立涵蓋特定時段的資料集的技巧是使用資料集的「開始時間」和「結束時間」參數。

使用「開始時間」和「結束時間」參數是其他技術的首選方法，例如移動日誌檔案以按目錄分隔它們。 透過設定資料集的開始和結束時間，資料工作台伺服器會自動僅使用在指定時間間隔內發生的記錄項目。 假設「結束時間」已過去，資料工作台伺服器通常會使用相同的記錄項目集來更新資料集，即使資料集是透過新增轉換來更新。

<!--
c_log_entry_con.xml
-->

## 記錄項目

實際上，它是對可用日誌條目的篩選過程。 如果[!DNL Log Entry Condition]返回值false，則從可用的日誌條目集中過濾日誌條目。

[!DNL Log Entry Condition]是通過使用條件操作（見[條件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)）來描述的，可以使用由[!DNL Sensor]Data Workbench[!DNL Sensor]指南&#x200B;*收集的任何輸入欄位或由[!DNL Log Processing.cfg]檔案中包含的轉換生成的任何擴展欄位來定義測試條件。*[!DNL Log Entry] 條件會在記錄處理期間套用，也可在轉換期間套用。

此範例示範如何使用[!DNL log entry condition]來處理網站資料。 您可以使用[!DNL Log Entry Condition]來建立資料集，以集中在網站的特定部分或在網站上執行特定動作的訪客。

此示例中的[!DNL Log Entry Condition]建立的資料集僅包含屬於站點儲存部分的日誌條目。 使用具有匹配模式[!DNL "/store/.*"]和[!DNL cs-uri-stem]欄位的[!DNL RECondition test]作為規則運算式的輸入，資料集中只包含以字串[!DNL "/store/"]開頭的網頁。

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## 密鑰拆分{#key-split}

資料集中的跟蹤ID數量人為增加，但資料工作台伺服器處理的日誌條目總數沒有人為增加，從而保留了資料集中可計數事件總數。 分割單一元素的資料後，資料會永遠與兩個不同的追蹤ID關聯，因此無法關聯。

例如，如果您使用的是Web資料，則每個追蹤ID代表一個獨特訪客。 如果您啟用金鑰分割，資料集中含有大量事件資料的訪客會分割為多個訪客。 雖然資料集中的訪客數量會人為增加，但可計數的事件（例如頁面檢視或預訂）總數不會人為增加。 發生分割後，子訪客的資料便無法關聯。

密鑰分割使用概率算法。 因此，在記憶體使用量、故障概率、密鑰拆分閾值([!DNL Split Key Bytes])和資料集大小之間存在折衷。 使用建議的設定（如下所列），失敗率很低。 在事件資料超過關鍵分割臨界值的元素中，約1/22,000（通常低於1個資料集）會截斷其部分資料，而非分割。

下表顯示每個參數的建議值（無索引鍵拆分和帶索引鍵拆分）。

| 參數 | 無密鑰拆分 | 密鑰拆分 |
|---|---|---|
| 組最大密鑰位元組數 | 1e6 | 2e6 |
| 分割關鍵時段空間 | 6e6 | 6e6 |
| 拆分鍵位元組 | 0 | 1e6 |
| 拆分鍵空間比 | 10 | 10 |

[!DNL Group Maximum Key Bytes] 指定可針對單一追蹤ID處理的事件資料量上限。從資料集建構程式中篩選超過此限制的資料。 [!DNL Split Key Bytes] 代表將單一追蹤ID分割為多個元素的位元組數。根據概率分佈，以大約這個數位元組來拆分元素。 [!DNL Split Key Space Ratio] 並控 [!DNL Split Key Bucket Space] 制密鑰拆分的記憶體利用率和故障率。

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes]、、 [!DNL Split Key Bytes]、 [!DNL Split Key Space Ratio]和 [!DNL Split Key Bucket Space] all必須聲明，密鑰拆分才能正常運作。不要在未咨詢Adobe的情況下更改這些參數的值。
