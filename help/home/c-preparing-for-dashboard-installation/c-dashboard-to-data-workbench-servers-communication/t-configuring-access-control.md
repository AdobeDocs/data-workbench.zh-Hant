---
description: 控制面板需要特定的唯讀權限才能存取和顯示您的資料工作台資料。 不需要寫權限。
solution: Analytics
title: 配置訪問控制
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 配置訪問控制{#configuring-access-control}

控制面板需要特定的唯讀權限才能存取和顯示您的資料工作台資料。 不需要寫權限。

設定存取控制需要 [!DNL Access Control.cfg] 在FSU上編輯檔案，並新增群組以授與資料工作台控制面板的權限：

1. 編輯文 [!DNL AccessControl.cfg] 件（最好使用資料工作台工作站）。
1. 建立名為 *Insight Dashboard Access的新群組*。
1. 在此群組的成員下，新增為此目的提供給您的適當CN(範例：CN:INSIGHT-USER01)。 如需此CN，請聯絡Adobe客戶服務。
1. 在此群組的唯讀存取權下，修改清單以反映下列項目：

* /Profiles/$
* /Profiles/
* /地址
* /狀態/
* /使用者/$

1. 從讀寫存取區移除任何項目，因為控制面板不需要寫入權限。
1. 將檔案的變更 [!DNL AccessControl.cfg] 儲存至伺服器，讓權限生效。
