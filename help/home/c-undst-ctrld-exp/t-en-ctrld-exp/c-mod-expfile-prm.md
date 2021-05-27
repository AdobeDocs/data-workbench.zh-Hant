---
description: ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。
solution: Analytics,Analytics
title: 修改 ExpFile 參數
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# 修改 ExpFile 參數{#modifying-the-expfile-parameter}

ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。

設定此參數可讓您執行實驗。 有關建立實驗配置檔案的步驟，請參閱[配置和部署實驗](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。

以下是ExpFile參數的範例：

```
ExpFile /home/experiment.txt
```

此定位符分隔的文本檔案([!DNL .txt])可以位於[!DNL Sensor]資料夾中的任意位置，並且可以有任何方便的名稱。

請務必記錄實驗目錄的位置以及您指定的配置檔案的名稱，因為您需要使用此名稱和此目錄中保存實驗配置檔案（將在本指南稍後介紹）。

>[!NOTE]
>
>如果您未在安裝[!DNL Sensor]的Web群集中的每台電腦上設定此參數相同，則受控實驗將無法工作。

此項可以預配置，並持續保留在[!DNL Sensor]配置檔案中，不會產生任何不良影響。 如果[!DNL Sensor]找不到指定的實驗配置檔案名或該檔案名為空（即存在，但無內容）,[!DNL Sensor]將不進行實驗，在HTTP伺服器上記錄錯誤事件，並在所有其他方面繼續正常運行。
