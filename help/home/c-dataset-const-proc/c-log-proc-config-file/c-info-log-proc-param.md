---
description: 連結至Log Processing.cfg檔案中特定參數的其他資訊。
title: 記錄處理參數
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# 記錄處理參數{#log-processing-parameters}

{{eol}}

連結至Log Processing.cfg檔案中特定參數的其他資訊。

<!--
c_data_filters.xml
-->

## 資料篩選器 {#data-filters}

在 [!DNL Log Processing.cfg] 檔案包含下列項目：

* 結束時間
* 雜湊臨界值
* 開始時間

由這些參數定義的篩選會在記錄項目離開解碼器之後以及轉換之後，但在由 [!DNL Log Entry Condition]. 一般而言，變更任何這些參數都會導致資料集的組成變更。

推薦的使用技術 [!DNL Sensor] 資料來源可建構涵蓋特定時段的資料集，是使用資料集的「開始時間」和「結束時間」參數。

與其他技術（如移動日誌檔案以按目錄分隔它們）相比，使用「開始時間」和「結束時間」參數是首選方法。 透過設定資料集的開始和結束時間，Data Workbench伺服器會自動僅使用在指定間隔內發生的記錄項目。 假設「結束時間」是過去的，Data Workbench伺服器通常會使用相同的記錄項目集來更新資料集，即使資料集的更新方式有，例如新增轉換。

<!--
c_log_entry_con.xml
-->

## 記錄項目

本質上，這是對可用日誌條目的篩選過程。 若 [!DNL Log Entry Condition] 傳回false值，則會從可用的記錄項目集中篩選出記錄項目。

此 [!DNL Log Entry Condition] 是透過使用條件操作來說明(請參閱 [條件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md))，並可使用收集的任何輸入欄位 [!DNL Sensor] (請參閱 *Data Workbench [!DNL Sensor] 指南* )或任何由包含在 [!DNL Log Processing.cfg] 檔案來定義測試條件。 [!DNL Log Entry] 條件會在記錄處理期間套用，並可在轉換期間選擇性地套用。

此範例示範如何使用 [!DNL log entry condition] ，以了解網站資料。 您可以使用 [!DNL Log Entry Condition] 建立以網站特定部分為焦點的資料集，或在網站上執行某些特定動作的訪客。

此 [!DNL Log Entry Condition] 在此範例中，會建立一個資料集，其中僅包含屬於網站存放區的記錄項目。 使用 [!DNL RECondition test] 匹配模式 [!DNL "/store/.*"] 和 [!DNL cs-uri-stem] 欄位作為規則運算式的輸入，僅限以字串開頭的網頁 [!DNL "/store/"] 包含在資料集中。

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## 鍵分割 {#key-split}

資料集中的追蹤ID數量會以人為方式增加，但Data Workbench伺服器處理的記錄項目總數不會以人為方式增加，因此可保留資料集中可數事件的總數。 分割單一元素的資料後，資料會永遠與兩個不同的追蹤ID相關聯，且無法相關。

例如，若您使用的是網路資料，每個追蹤ID代表一個不重複訪客。 如果您啟用金鑰分割，資料集中含有大量事件資料的訪客會分割為多個訪客。 雖然資料集中的訪客數量是人為增加的，但可數事件（例如頁面檢視或預訂）的總數並非人為增加。 發生分割後，子訪客的資料便無法關聯。

密鑰拆分使用概率算法。 因此，在記憶體使用、故障概率、密鑰拆分閾值( [!DNL Split Key Bytes])和資料集大小。 若使用建議的設定（如下所列），則失敗率很低。 在事件資料超過關鍵拆分臨界值的元素中，大約22,000分之1（通常每個資料集少於1）的某些資料會遭到截斷，而非拆分。

下表顯示每個參數的建議值（不含和包含索引鍵拆分）。

| 參數 | 無鍵拆分 | 密鑰拆分 |
|---|---|---|
| 組最大密鑰位元組數 | 1e6 | 2e6 |
| 拆分鍵桶空間 | 6e6 | 6e6 |
| 拆分鍵位元組 | 0 | 1e6 |
| 拆分鍵空間比 | 10 | 10 |

[!DNL Group Maximum Key Bytes] 指定可針對單一追蹤ID處理的事件資料量上限。 超過此限制的資料會從資料集建構程式中篩選。 [!DNL Split Key Bytes] 代表將單一追蹤ID分割為多個元素的位元組數。 元素會根據概率分佈以大約此數位元組來分割。 [!DNL Split Key Space Ratio] 和 [!DNL Split Key Bucket Space] 控制密鑰拆分的記憶體利用率和故障率。

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio]，和 [!DNL Split Key Bucket Space] 必須宣告全部，密鑰分割才能正常運作。 若沒有諮詢Adobe，請勿變更這些參數的值。
