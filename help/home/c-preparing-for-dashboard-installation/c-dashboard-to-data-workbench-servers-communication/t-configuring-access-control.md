---
description: 控制面板需要特定的唯讀權限，才能存取和顯示您的Data Workbench資料。 不需要寫權限。
title: 設定控制面板存取控制
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: 90b9fff995cb37a62024f454f009e9e0d7b927cd
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 2%

---

# 設定控制面板存取控制{#configuring-dashboard-access-control}

{{eol}}

控制面板需要特定的唯讀權限，才能存取和顯示您的Data Workbench資料。 不需要寫權限。

設定存取控制需要編輯 [!DNL Access Control.cfg] 檔案，並新增新群組以授與Data Workbench控制面板的權限：

1. 編輯 [!DNL AccessControl.cfg] 檔案（最好使用data workbench工作站）。
1. 建立名為 *Insight Dashboard存取*.
1. 在此群組成員下，新增為此目的提供給您的正確CN(範例：CN:INSIGHT-USER01)。 如需此CN，請聯絡Adobe客戶服務。
1. 在此組的只讀訪問下，修改清單以反映以下內容：

* /設定檔/$
* /設定檔/
* /地址
* /狀態/
* /用戶/$

1. 從讀寫訪問部分刪除任何項，因為控制面板不需要寫權限。
1. 將變更儲存至 [!DNL AccessControl.cfg] 檔案傳送至伺服器，讓權限生效。
