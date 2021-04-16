---
description: Insight Server中時間型參數的格式指示。
title: 時區代碼
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# 時區代碼{#time-zone-codes}

Insight Server中時間型參數的格式指示。

[!DNL Insight Server]中大多數基於時間的參數都以下列格式指定：

*月DD, YYYY HH:MM:SS時區*

範例：2013年8月13日美國東部標準時22點30分

時區以下列格式的獨立於系統的時區格式（協調通用時間）表示：

UTC +hhmm *dstrules*

符號(+)可以是加號(+)或減號(-),*hhmm*&#x200B;是以小時和分鐘錶示的與UTC的偏移。 可選變數&#x200B;*dstrules*&#x200B;指定一組規則以實施日光節約時間或類似的時鐘移位策略。

如果您指定&#x200B;*dstrules*，則名為&#x200B;*[!DNL dstrules]*[!DNL .dst]的Tab字元分隔檔案必須存在於基本設定檔的Dataset\TimeZone目錄中（用於未與特定資料集關聯的設定檔）或資料集描述檔（用於特定資料集的設定檔）。 檔案指定日光節約時間的一組與時區無關的規則。 您可以針對不同的年份使用不同的規則集。 基本配置檔案中由Adobe提供的[!DNL DST.dst]檔案指定了2005年能源政策法案（2007年起生效）所確立的標準美國規則和美國規則。

以下列出時區條目示例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* 無偏移和無&#x200B;*dstrules*&#x200B;的UTC時間（對應於GMT）:時區=字串：UTC -0000

使用此格式時，[!DNL Insight Server]、[!DNL Insight]和[!DNL Report]電腦的系統時區不必與指定的時區相同。 此外，[!DNL Insight Server]機器上所有作用中的資料集描述檔都不需要相同的時區設定。

下表包含可用於在時間參數中指定時區的代碼清單。

## 時區代碼表{#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>如果要實施日光節約時間或類似的時鐘移位策略，則必須保存[!DNL .dst]檔案，該檔案包含&#x200B;*配置檔案名*\Dataset\Timezone directory on the [!DNL Insight Server]電腦中的相應規則。

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
