---
description: Insight Server中以時間為基礎之參數的格式說明。
title: 時區代碼
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# 時區代碼{#time-zone-codes}

Insight Server中以時間為基礎之參數的格式說明。

[!DNL Insight Server]中大多數基於時間的參數都以以下格式指定：

*月DD, YYYY HH:MM:SS時區*

範例：2013年8月13日東22:30:00年

時區以下列格式表示為系統獨立時區格式（協調通用時間）:

UTC +hhmm *dstrules*

符號(+)可以是加號(+)或減號(-)，而&#x200B;*hhmm*&#x200B;是以小時和分鐘為單位從UTC偏移。 可選變數&#x200B;*dstrules*&#x200B;指定一組用於實施日光節約時間的規則或類似的時鐘轉移策略。

如果指定&#x200B;*dstrules*，則名為&#x200B;*&lt; [!DNL dstrules]>* [!DNL .dst]的定位符分隔檔案必須存在於基本配置檔案的「資料集\時區」目錄中（用於未與特定資料集關聯的配置檔案）或資料集配置檔案中（用於特定於資料集的配置檔案）。 此檔案指定日光節約時間的一組獨立於時區的規則。 您可以針對不同的年份使用不同的規則集。 Base配置檔案中由Adobe提供的[!DNL DST.dst]檔案指定了2005年《能源政策法》（2007年起生效）所確立的標準美國規則和美國規則。

以下列出時區項目範例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* 無偏移和無&#x200B;*dstrules*&#x200B;的UTC時間（與GMT對應）:時區=字串：UTC -0000

使用此格式時，[!DNL Insight Server]、[!DNL Insight]和[!DNL Report]電腦的系統時區不一定與指定時區相同。 此外，[!DNL Insight Server]電腦上所有作用中資料集設定檔都不需要相同的時區設定。

下表包含可用於在時間參數中指定時區的代碼清單。

## 時區代碼表{#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>如果要實施日光節約時間或類似的時鐘轉移策略，必須在&#x200B;*配置檔案名稱*\Dataset\Timezone directory on the [!DNL Insight Server]電腦中保存包含相應規則的[!DNL .dst]檔案。

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
