---
description: Transformation.cfg檔案中的時區參數可控制時間維度、時間轉換（例如，定義x-local-timestring欄位），以及資料集描述檔中所有本機時間的格式。
solution: Analytics
title: 時區
topic: Data workbench
uuid: 7b253c5a-f2b1-410c-9433-f13ed1d7a8b3
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 時區{#time-zones}

Transformation.cfg檔案中的時區參數可控制時間維度、時間轉換（例如，定義x-local-timestring欄位），以及資料集描述檔中所有本機時間的格式。

>[!NOTE]
>
>「時區」參數不會影響系統層級的功能，例如狀態中的時間戳記和事件記錄檔，這些會在系統本地時間中表示。

時區參數支援下列格式的獨立於系統的時區格式（「協調通用時間」）:

時區=字串：UTC +hhmm dstrules

符號(+)可以是加號(+)或減號(-), *hhmm* 是在數小時和數分鐘內偏離UTC。 可選變 *數dstrules* 指定一組規則，用於實施日光節約時間或類似的時鐘移位策略。

如果您指 *定dstrules*，則名為Tab分隔的檔案 [!DNL dstrules .dst] 必須存在於資料集描述檔的Dataset\TimeZone子目錄中。 檔案指定日光節約時間的一組與時區無關的規則。 您可以針對不同的年份使用不同的規則集。 Adobe [!DNL DST.dst] 在基本設定檔中提供的檔案會指定2005年《能源政策法案》（Energy Policy Act of 2007年起生效）所訂定的標準美國規則，以及過去數年的美國規則。

「時區」條目示例列於以下：

* 美國東部夏令時：時區=字串：UTC -0500 DST
* UTC時間，無偏移，無規則：時區=字串：UTC -0000

使用此格式時，資料工作台伺服器、資料工作台和機器的系統時區 [!DNL Report] ，不需與指定時區相同。 此外，資料工作台伺服器上所有作用中的資料集設定檔不需要具有相同的時區設定。

Adobe不建議在單一資料工作台伺服器機器或資料工作台伺服器叢集上執行多個資料集描述檔。

資料工作台使用者會在資料集描述檔的時區中看到資料，而非其系統時區。 Adobe建議資料工作台伺服器電腦的系統時區與其資料集中使用的時區相同。

>[!NOTE]
>
>您可以在檔案中指定時區參 [!DNL Log Processing.cfg] 數，用於記錄處理期間的時間轉換。 如需檔案中「時區」參數的詳細資訊，請 [!DNL Log Processing.cfg] 參閱記 [錄處理設定檔](../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)。

