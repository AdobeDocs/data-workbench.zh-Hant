---
description: 關於時區代碼和格式的資訊。
title: 時區代碼和格式
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 4%

---

# 時區代碼{#time-zone-codes}

{{eol}}

關於時區代碼和格式的資訊。

Data Workbench伺服器中大部分以時間為基礎的參數皆以下列格式指定：

* 月DD , YYYY HH :MM :SS TZone
* 範例：2013年8月13日22:30:東部標準時間00

時區以下列格式表示為系統獨立時區格式（協調通用時間）:

* UTC +hhmm dstrules

符號(+)可以是加號(+)或減號(-),hhmm是以小時和分鐘計從UTC偏移的。 可選變數設定指定一組用於實施日光節約時間的規則或類似的時鐘切換策略。

如果您指定規則，則會以Tab分隔的檔案命名為 [!DNL dstrules.dst] 必須位於 [!DNL Base] 設定檔（適用於未與特定資料集關聯的設定檔）或資料集設定檔（適用於資料集專用的設定檔）。 此檔案指定日光節約時間的一組獨立於時區的規則。 您可以針對不同的年份使用不同的規則集。 此 [!DNL DST.dst] 由Adobe提供的檔案 [!DNL Base] 設定檔具體規定了2005年《能源政策法》（2007年起生效）所確立的美國標準規則，以及美國以往年份的規則。

以下列出時區項目範例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* UTC時間（沒有偏移和沒有分組）（與GMT對應）:時區=字串：UTC -0000

使用此格式時，Data Workbench伺服器、Data Workbench和報表電腦的系統時區不一定與指定時區相同。 此外，Data Workbench伺服器電腦上所有作用中的資料集設定檔都不需要相同的時區設定。

下表包含可用於在時間參數中指定時區的代碼清單。

## 時區代碼表 {#section-b4f965b872c543e2ac52a3c94410d076}

若您正在實施日光節約時間或類似的時鐘轉移政策，則必須儲存 [!DNL .dst] 在設定檔名稱中包含適當規則的檔案 [!DNL \Dataset\Timezone] 資料工作台伺服器電腦上的目錄。

| 程式碼 | 時區 | GMT時差 |
|---|---|---|
| gmt | 格林威治中值 | 0 |
| est | 東部標準 | 5 |
| edt | 東日光 | 5 |
| cst | 中央標準 | 6 |
| cdt | 中央日光 | 6 |
| mst | 山區標準 | 7 |
| mdt | 山光 | 7 |
| pst | 太平洋標準 | 8 |
| pdt | 太平洋日光 | 8 |
