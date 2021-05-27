---
description: Data Workbench可設定為僅允許特定使用者變更特定工作區。
title: 設定鎖定的工作區
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# 設定鎖定的工作區{#configure-a-locked-workspace}

Data Workbench可設定為僅允許特定使用者變更特定工作區。

鎖定工作區時，使用者可以在大部分的視覺效果中進行選取，並排序表格中的資料，但無法變更工作區。 此功能可防止使用者對工作區進行無意的變更。

以下三個元素可共同控制工作區的鎖定：

* **資料夾.lock或工 *作區名稱*.lock檔案：** 檔案 [!DNL folder.lock] 指定是否鎖定特定資料夾中的工作區，而工作區檔案 [!DNL name.lock] 指定是否鎖定特定工作區。

* **使用者檔案中的「解除鎖定」參 [!DNL Insight.cfg] 數：** 此參數會指定該使用者是否可暫時解除鎖定的工作區鎖定。
* **「暫時解除鎖定」功能表選項：** 當使用者的「解除鎖定」 [!DNL Insight.cfg] 參數設為true時，此選項會自動出現在每個鎖定工作區的標題列功能表中，為使用者解除鎖定提供方式。

有關[!DNL folder.lock]和工作區[!DNL name.lock]檔案的資訊，請參閱以下部分。 有關設定Unlock參數的資訊，請參閱[設定Unlock參數](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)。 有關[!DNL Temporarily Unlock menu]選項的資訊，請參閱[解鎖工作區](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)。
