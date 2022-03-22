---
description: 設定有關Insight Server中基於時間的參數的說明的格式。
title: 時區代碼(Insight Server)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---

# 時區代碼{#time-zone-codes}

設定有關Insight Server中基於時間的參數的說明的格式。

中的大多數基於時間的參數 [!DNL Insight Server] 以下格式指定：

*月DD,YYYY HH:MM:SS時區*

示例：2013年8月13日22:30:東部時間00

時區以以下格式的獨立於系統的時區格式（協調通用時間）表示：

UTC +hhmm *腳*

符號(+)可以是加號(+)或減號(-)，並且 *哼* 是以小時和分鐘錶示的與UTC的偏移量。 可選變數 *腳* 指定一組用於實施夏令時或類似時鐘切換策略的規則。

如果指定 *腳*，以制表符分隔的檔案 *&lt; [!DNL dstrules]>* [!DNL .dst] 必須在基本配置檔案（對於與特定資料集不關聯的配置檔案）或資料集配置檔案（對於特定於資料集的配置檔案）的Dataset\TimeZone目錄中。 該檔案為夏令時指定一組獨立於時區的規則。 你可以有不同的規則來適應不同的年份。 的 [!DNL DST.dst] 基本配置檔案中由Adobe提供的檔案指定了2005年《能源政策法》（實際從2007年開始）制定的標準美國規則以及美國在以往年份制定的規則。

下面列出了示例時區條目：

* 美國東部夏令時：時區=字串：UTC -0500夏時
* UTC時間，無偏移，無 *腳* （對應於GMT）:時區=字串：UTC -0000

使用此格式時，系統時區 [!DNL Insight Server]。 [!DNL Insight], [!DNL Report] 電腦不必與指定的時區相同。 此外， [!DNL Insight Server] 電腦不需要具有相同的時區設定。

下表包含可用於在基於時間的參數中指定時區的代碼清單。

## 時區代碼表 {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>如果要實施夏令時或類似的時鐘切換策略，則必須保存 [!DNL .dst] 檔案中包含 *配置檔案名稱*\Dataset\Timezone目錄 [!DNL Insight Server] 機器。

| 程式碼 | 時區 | 從GMT偏移 |
|---|---|---|
| gmt | 格林威治中線 | 0 |
| est | 東部標準 | 5 |
| 東 | 東夏 | 5 |
| 科技 | 中央標準 | 6 |
| 卡特 | 中央夏令時 | 6 |
| 最小 | 山標 | 7 |
| mdt | 山間夏令時 | 7 |
| past（後期） | 太平洋標準 | 8 |
| pdt | 太平洋夏令時 | 8 |
