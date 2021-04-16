---
description: 有關時區代碼和格式的資訊。
title: 時區代碼
uuid: 5698882a-9682-41d8-88d3-8471578a22cc
exl-id: 2829c4ca-af6f-4ddb-acce-b33c3b552ba7
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 5%

---

# 時區代碼{#time-zone-codes}

有關時區代碼和格式的資訊。

資料工作台伺服器中大部分以時間為基礎的參數皆以下列格式指定：

* 月DD, YYYY HH:MM:SS TZone
* 範例：2013年8月13日美國東部標準時22點30分

時區以下列格式的獨立於系統的時區格式（協調通用時間）表示：

* UTC +hhmm dstrules

符號(+)可以是加號(+)或減號(-),hhmm是在數小時和數分鐘內偏離UTC的位置。 可選變數規則會指定一組規則，以實作日光節約時間或類似的時鐘移位政策。

如果指定規則，則[!DNL Base]描述檔的Dataset\TimeZone目錄中必須存在名為[!DNL dstrules.dst]的Tab分隔檔案（對於未與特定資料集關聯的設定檔）或資料集描述檔（對於資料集特定的設定檔）。 檔案指定日光節約時間的一組與時區無關的規則。 您可以針對不同的年份使用不同的規則集。 [!DNL Base]設定檔中由Adobe提供的[!DNL DST.dst]檔案，指定2005年能源政策法案（2007年起生效）所訂定的美國標準規則及美國過往年度規則。

以下列出時區條目示例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* UTC時間（無偏移和無規則）（對應於GMT）:時區=字串：UTC -0000

使用此格式時，資料工作台伺服器、資料工作台和報表機器的系統時區不必與指定時區相同。 此外，資料工作台伺服器上所有作用中的資料集設定檔不需要具有相同的時區設定。

下表包含可用於在時間參數中指定時區的代碼清單。

## 時區代碼表{#section-b4f965b872c543e2ac52a3c94410d076}

如果要實施日光節約時間或類似的時鐘移位策略，則必須保存資料工作台伺服器電腦上配置檔案名稱[!DNL \Dataset\Timezone]目錄中包含相應規則的[!DNL .dst]檔案。

| 程式碼 | 時區 | 偏離GMT |
|---|---|---|
| gmt | 格林威治標準時間 | 0 |
| est | Eastern Standard | 5 |
| edt | 東日光 | 5 |
| cst | Central Standard | 6 |
| cdt | 中央日光 | 6 |
| mst | Mountain Standard | 7 |
| mdt | 山地日光 | 7 |
| pst | Pacific Standard | 8 |
| pdt | 太平洋日光 | 8 |
