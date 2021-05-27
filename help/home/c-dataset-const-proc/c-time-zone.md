---
description: 關於時區代碼和格式的資訊。
title: 時區代碼
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 5%

---

# 時區代碼{#time-zone-codes}

關於時區代碼和格式的資訊。

Data Workbench伺服器中大部分以時間為基礎的參數皆以下列格式指定：

* 月DD , YYYY HH :MM :SS TZone
* 範例：2013年8月13日東22:30:00年

時區以下列格式表示為系統獨立時區格式（協調通用時間）:

* UTC +hhmm dstrules

符號(+)可以是加號(+)或減號(-),hhmm是以小時和分鐘計從UTC偏移的。 可選變數設定指定一組用於實施日光節約時間的規則或類似的時鐘切換策略。

如果指定規則，[!DNL Base]配置檔案的「資料集\時區」目錄（針對未與特定資料集關聯的配置檔案）或資料集配置檔案（針對特定於資料集的配置檔案）中必須存在名為[!DNL dstrules.dst]的以定位點分隔的檔案。 此檔案指定日光節約時間的一組獨立於時區的規則。 您可以針對不同的年份使用不同的規則集。 [!DNL Base]配置檔案中由Adobe提供的[!DNL DST.dst]檔案指定了2005年《能源政策法》（自2007年起生效）和美國以前年度的規則所確立的標準美國規則。

以下列出時區項目範例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* UTC時間（沒有偏移和沒有分組）（與GMT對應）:時區=字串：UTC -0000

使用此格式時，Data Workbench伺服器、Data Workbench和報表電腦的系統時區不一定與指定時區相同。 此外，Data Workbench伺服器電腦上所有作用中的資料集設定檔都不需要相同的時區設定。

下表包含可用於在時間參數中指定時區的代碼清單。

## 時區代碼表{#section-b4f965b872c543e2ac52a3c94410d076}

若您正在實作日光節約時間或類似的時鐘轉移政策，您必須在Data Workbench伺服器電腦的設定檔名稱[!DNL \Dataset\Timezone]目錄中，儲存包含適當規則的[!DNL .dst]檔案。

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
