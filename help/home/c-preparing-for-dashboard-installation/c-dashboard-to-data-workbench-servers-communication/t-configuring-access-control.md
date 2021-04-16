---
description: 控制面板需要特定的唯讀權限才能存取和顯示您的資料工作台資料。 不需要寫權限。
title: 設定存取控制
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# 設定存取控制{#configuring-access-control}

控制面板需要特定的唯讀權限才能存取和顯示您的資料工作台資料。 不需要寫權限。

設定存取控制需要編輯FSU上的[!DNL Access Control.cfg]檔案，並新增群組以授與資料工作台控制面板的權限：

1. 編輯[!DNL AccessControl.cfg]檔案（最好使用資料工作台工作站）。
1. 建立名為&#x200B;*Insight Dashboard Access*&#x200B;的新群組。
1. 在此群組的成員下，新增為此目的提供給您的適當CN(範例：CN:INSIGHT-USER01)。 請聯絡Adobe客戶服務以取得此CN。
1. 在此群組的唯讀存取權下，修改清單以反映下列項目：

* /設定檔/$
* /設定檔/
* /地址
* /狀態/
* /使用者/$

1. 從讀寫存取區移除任何項目，因為控制面板不需要寫入權限。
1. 將對[!DNL AccessControl.cfg]檔案所做的更改保存到伺服器以使權限生效。
