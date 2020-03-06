---
description: ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。
solution: Insight,Analytics
title: 修改ExpFile參數
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改ExpFile參數{#modifying-the-expfile-parameter}

ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。

設定此參數可讓您執行實驗。 如需建立實驗設定檔案的步驟，請參 [閱設定和部署實驗](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。

以下是ExpFile參數的示例：

```
ExpFile /home/experiment.txt
```

此Tab分隔文字檔( [!DNL .txt])可位於資料夾中的任 [!DNL Sensor] 何位置，而且可以有任何方便的名稱。

請務必記錄實驗目錄的位置和您指定的配置檔案的名稱，因為您需要使用此名稱和此目錄中保存實驗配置檔案（本指南稍後將說明）。

>[!NOTE]
>
>如果您未在安裝Web群集的每台機器上相同地設定此參數，則 [!DNL Sensor] 控制實驗將無法運作。

可以預配置此條目，並且可以持 [!DNL Sensor] 續保留在配置檔案中，不會產生任何不良影響。 如果指定的實驗配置檔案名未被找到或為空 [!DNL Sensor] （即，它存在但沒有內容），則不執行實驗，在 [!DNL Sensor] HTTP伺服器上記錄錯誤事件，並在所有其他方面繼續正常運行。
