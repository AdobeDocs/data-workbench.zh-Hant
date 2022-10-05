---
description: Insight Server中以時間為基礎之參數的格式說明。
title: 時區代碼(Insight Server)
uuid: dcc8aa15-5846-4f24-8b82-e25ff89871ba
exl-id: d8923b01-24fe-4a70-9800-f2eedf567c6a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 4%

---

# 時區代碼{#time-zone-codes}

{{eol}}

Insight Server中以時間為基礎之參數的格式說明。

中大多數以時間為基礎的參數 [!DNL Insight Server] 會以下列格式指定：

*月DD, YYYY HH:MM:SS時區*

範例：2013年8月13日22:30:東部標準時間00

時區以下列格式表示為系統獨立時區格式（協調通用時間）:

UTC +hhmm *dstrules*

符號(+)可以是加號(+)或減號(-)，以及 *hhmm* 是以小時和分鐘為單位的與UTC的偏移。 選用變數 *dstrules* 指定一組用於實施日光節約時間的規則或類似的時鐘切換策略。

如果您指定 *dstrules*，此檔案名為 *&lt; [!DNL dstrules]>* [!DNL .dst] 基本配置檔案的「資料集\時區」目錄中必須存在（用於未與特定資料集關聯的配置檔案）或資料集配置檔案（用於特定於資料集的配置檔案）。 此檔案指定日光節約時間的一組獨立於時區的規則。 您可以針對不同的年份使用不同的規則集。 此 [!DNL DST.dst] 「基本」配置檔案中由Adobe提供的檔案指定了2005年《能源政策法》（2007年起生效）規定的美國標準規則以及美國以前年份的規則。

以下列出時區項目範例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* 無偏移和無的UTC時間 *dstrules* （對應於GMT）:時區=字串：UTC -0000

使用此格式時，系統時區 [!DNL Insight Server], [!DNL Insight]，和 [!DNL Report] 電腦不需要與指定的時區相同。 此外， [!DNL Insight Server] 電腦不需要相同的時區設定。

下表包含可用於在時間參數中指定時區的代碼清單。

## 時區代碼表 {#section-3cab225b864f4e54ac4f5bd83ab4ed36}

>[!NOTE]
>
>若您正在實施日光節約時間或類似的時鐘轉移政策，則必須儲存 [!DNL .dst] 檔案中包含 *設定檔名稱*\資料集\時區目錄 [!DNL Insight Server] 機器。

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
