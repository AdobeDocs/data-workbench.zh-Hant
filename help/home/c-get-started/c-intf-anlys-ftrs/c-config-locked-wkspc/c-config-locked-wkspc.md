---
description: Data Workbench可設定為僅允許特定使用者變更特定工作區。
title: 設定鎖定的工作區
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# 設定鎖定的工作區{#configure-a-locked-workspace}

Data Workbench可設定為僅允許特定使用者變更特定工作區。

當工作區鎖定時，使用者可以在大多數視覺化中進行選擇，並排序表格中的資料，但無法變更工作區。 此功能可防止使用者對工作區進行無意的變更。

以下三個元素可搭配運作以控制工作區的鎖定：

* **folder.lock或工 *作區名稱*.lock檔案：文** 件指定是否鎖定特定資料夾中的工作區，而工作區 [!DNL folder.lock]  [!DNL name.lock] 檔案指定是否鎖定特定工作區。

* **使用者檔案中的「解除鎖定」參 [!DNL Insight.cfg] 數：此** 參數會指定該使用者是否可暫時解除鎖定的工作區。
* **「暫時解除鎖定」功能表選項：當使用者的「解除鎖定」參數設為**  [!DNL Insight.cfg] true時，此選項會自動出現在每個已鎖定工作區的標題列功能表中，讓使用者可以解除鎖定。

有關[!DNL folder.lock]和工作區[!DNL name.lock]檔案的資訊，請參見以下部分。 有關設定解鎖參數的資訊，請參閱[設定解鎖參數](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)。 有關[!DNL Temporarily Unlock menu]選項的資訊，請參閱[解除鎖定工作區](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)。
