---
description: 「資料工作台」可設定為僅允許特定使用者變更特定工作區。
solution: Analytics
title: 配置鎖定的工作區
topic: Data workbench
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置鎖定的工作區{#configure-a-locked-workspace}

「資料工作台」可設定為僅允許特定使用者變更特定工作區。

當工作區鎖定時，使用者可以在大多數視覺化中進行選擇，並排序表格中的資料，但無法變更工作區。 此功能可防止使用者對工作區進行無意的變更。

以下三個元素可搭配運作以控制工作區的鎖定：

* **資料夾。lock或工&#x200B;*作區名稱*.lock檔案：** 文 [!DNL folder.lock] 件指定是否鎖定特定資料夾中的工作區，而工作區檔案 [!DNL name.lock] 指定是否鎖定特定工作區。

* **使用者檔案中的「解除鎖定」參[!DNL Insight.cfg]數：** 此參數指定該用戶是否可以臨時解鎖鎖定的工作區。
* **「暫時解除鎖定」功能表選項：** 當使用者的「解除鎖定」參數設 [!DNL Insight.cfg] 定為true時，此選項會自動出現在每個已鎖定工作區的標題列選單中，讓使用者可以解除鎖定。

如需有關和工 [!DNL folder.lock] 作區檔案 [!DNL name.lock] 的資訊，請參閱下一節。 有關設定解鎖參數的資訊，請參 [閱設定解鎖參數](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)。 有關該選項的信 [!DNL Temporarily Unlock menu] 息，請參 [閱解鎖工作區](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e)。
