---
description: Transformation.cfg檔案中的Time Zone參數可控制時間維度、時間轉換（例如，定義x-local-timestring欄位），以及資料集設定檔中所有本地時間的格式。
title: 時區
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# 時區{#time-zones}

{{eol}}

Transformation.cfg檔案中的Time Zone參數可控制時間維度、時間轉換（例如，定義x-local-timestring欄位），以及資料集設定檔中所有本地時間的格式。

>[!NOTE]
>
>「時區」參數不會影響系統層級功能，例如狀態中的時間戳和事件記錄，以系統當地時間表示。

時區參數支援以下格式的獨立於系統的時區格式（「協調通用時間」）:

時區=字串：UTC +hhmm dstrules

符號(+)可以是加號(+)或減號(-)，以及 *hhmm* 是以小時和分鐘為單位的與UTC的偏移。 選用變數 *dstrules* 指定一組用於實施日光節約時間的規則或類似的時鐘切換策略。

如果您指定 *dstrules*，此檔案名為 [!DNL dstrules .dst] 必須位於資料集描述檔的「資料集\時區」子目錄中。 此檔案指定日光節約時間的一組獨立於時區的規則。 您可以針對不同的年份使用不同的規則集。 此 [!DNL DST.dst] 「基本」配置檔案中由Adobe提供的檔案指定了2005年《能源政策法》（2007年起生效）規定的美國標準規則以及美國以前年份的規則。

以下列出時區項目範例：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* UTC時間（沒有偏移和無規則）:時區=字串：UTC -0000

使用此格式時，Data Workbench伺服器、Data Workbench和 [!DNL Report] 電腦不需要與指定的時區相同。 此外，Data Workbench伺服器電腦上所有作用中的資料集設定檔都不需要相同的時區設定。

Adobe不建議在單一Data Workbench伺服器電腦或Data Workbench伺服器叢集上執行多個資料集設定檔。

Data Workbench使用者可在資料集設定檔的時區（而非其系統時區）中看到資料。 Adobe建議Data Workbench伺服器電腦的系統時區與其資料集中使用的時區相同。

>[!NOTE]
>
>您可以在 [!DNL Log Processing.cfg] 檔案中，記錄處理期間會用於時間轉換。 如需 [!DNL Log Processing.cfg] 檔案，請參閱 [記錄處理組態檔](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).
