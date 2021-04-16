---
description: Transformation.cfg檔案中的時區參數可控制時間維度、時間轉換（例如，定義x-local-timestring欄位），以及資料集描述檔中所有本機時間的格式。
title: 時區
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
exl-id: c8dc49d5-3245-428a-bfb9-42970df73d3e
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 1%

---

# 時區{#time-zones}

Transformation.cfg檔案中的時區參數可控制時間維度、時間轉換（例如，定義x-local-timestring欄位），以及資料集描述檔中所有本機時間的格式。

>[!NOTE]
>
>「時區」參數不會影響系統層級的功能，例如狀態中的時間戳記和事件記錄檔，這些會在系統本地時間中表示。

時區參數支援下列格式的獨立於系統的時區格式（「協調通用時間」）:

時區=字串：UTC +hhmm dstrules

符號(+)可以是加號(+)或減號(-),*hhmm*&#x200B;是以小時和分鐘錶示的與UTC的偏移。 可選變數&#x200B;*dstrules*&#x200B;指定一組規則以實施日光節約時間或類似的時鐘移位策略。

如果指定&#x200B;*dstrules*，則名為[!DNL dstrules .dst]的定位點分隔檔案必須存在於資料集描述檔的Dataset\TimeZone子目錄中。 檔案指定日光節約時間的一組與時區無關的規則。 您可以針對不同的年份使用不同的規則集。 基本配置檔案中由Adobe提供的[!DNL DST.dst]檔案指定了2005年能源政策法案（2007年起生效）所確立的標準美國規則和美國規則。

「時區」條目示例列於以下：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* UTC時間，無偏移，無規則：時區=字串：UTC -0000

使用此格式時，資料工作台伺服器、資料工作台和[!DNL Report]機器的系統時區不必與指定時區相同。 此外，資料工作台伺服器上所有作用中的資料集設定檔不需要具有相同的時區設定。

Adobe不建議在單一資料工作台伺服器機器或資料工作台伺服器叢集上執行多個資料集描述檔。

資料工作台使用者會在資料集描述檔的時區中看到資料，而非其系統時區。 Adobe建議資料工作台伺服器電腦的系統時區與其資料集中使用的時區相同。

>[!NOTE]
>
>您可以在[!DNL Log Processing.cfg]檔案中指定時區參數，用於記錄處理期間的時間轉換。 有關[!DNL Log Processing.cfg]檔案中的時區參數的資訊，請參見[日誌處理配置檔案](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。
