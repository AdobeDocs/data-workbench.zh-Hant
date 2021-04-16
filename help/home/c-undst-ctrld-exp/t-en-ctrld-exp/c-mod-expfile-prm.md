---
description: ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。
solution: Analytics,Analytics
title: 修改 ExpFile 參數
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# 修改 ExpFile 參數{#modifying-the-expfile-parameter}

ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。

設定此參數可讓您執行實驗。 有關建立實驗配置檔案的步驟，請參見[配置和部署實驗](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。

以下是ExpFile參數的示例：

```
ExpFile /home/experiment.txt
```

此Tab分隔的文字檔案([!DNL .txt])可位於[!DNL Sensor]檔案夾中的任何位置，並可使用任何方便的名稱。

請務必記錄實驗目錄的位置和您指定的配置檔案的名稱，因為您需要使用此名稱和此目錄中保存實驗配置檔案（本指南稍後將說明）。

>[!NOTE]
>
>如果您未在安裝[!DNL Sensor]的Web群集中的每台機器上相同地設定此參數，則無法進行受控實驗。

可以預配置此條目，並且持續保留在[!DNL Sensor]配置檔案中，不產生任何不良影響。 如果[!DNL Sensor]找不到指定的實驗配置檔案名或它為空（即，它存在但沒有內容）,[!DNL Sensor]不進行實驗，在HTTP伺服器上記錄錯誤事件，並在所有其它方面繼續正常運行。
