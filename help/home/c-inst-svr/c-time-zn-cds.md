---
description: Insight Server中時間型參數的格式指示。
solution: Insight
title: 時區代碼
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 時區代碼{#time-zone-codes}

Insight Server中時間型參數的格式指示。

中大多數基於時間的參 [!DNL Insight Server] 數都以下列格式指定：

*月DD, YYYY HH:MM:SS時區*

範例：2013年8月13日美國東部標準時22點30分

時區以下列格式的獨立於系統的時區格式（協調通用時間）表示：

UTC +hhmm *dstrules*

符號(+)可以是加號(+)或減號(-), *hhmm* 是在數小時和數分鐘內偏離UTC。 可選變 *數dstrules* 指定一組規則，用於實施日光節約時間或類似的時鐘移位策略。

如果指 *定dstrules*，則基本配置檔案（對於與特定資料集無關的配置檔案）或資料集配置檔案（對於特定於資料集的配置檔案）的Dataset\TimeZone目錄中必須存在名為 *&lt;[!DNL dstrules]*[!DNL .dst] >的Tab分隔檔案。 檔案指定日光節約時間的一組與時區無關的規則。 您可以針對不同的年份使用不同的規則集。 Adobe [!DNL DST.dst] 在基本設定檔中提供的檔案會指定2005年《能源政策法案》（Energy Policy Act of 2007年起生效）所訂定的標準美國規則，以及過去數年的美國規則。

以下列出時區條目示例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* UTC時間(無偏移和無 *規則* )（對應於GMT）:時區=字串：UTC -0000

使用此格式時，系統的、 [!DNL Insight Server]和 [!DNL Insight][!DNL Report] 電腦時區不必與指定的時區相同。 此外，機器上所有作用中的資料集 [!DNL Insight Server] 設定檔都不需要有相同的時區設定。

下表包含可用於在時間參數中指定時區的代碼清單。

## 時區代碼表 {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>如果要實施日光節約時間或類似的時鐘移位策略，則必須在配置檔案名 [!DNL .dst] \Dataset\Timezone directory on the 電腦中保存包含相 *應規*&#x200B;則的文 [!DNL Insight Server] 件。

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

