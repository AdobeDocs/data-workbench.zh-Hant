---
description: ExpFile參數指向實驗配置檔案的位置，該配置檔案定義了您的實驗。
solution: Analytics
title: 修改 ExpFile 參數
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# 修改 ExpFile 參數{#modifying-the-expfile-parameter}

ExpFile參數指向實驗配置檔案的位置，該配置檔案定義了您的實驗。

通過設定此參數，可以運行實驗。 有關建立實驗配置檔案的步驟，請參見 [配置和部署實驗](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429)。

以下是ExpFile參數的示例：

```
ExpFile /home/experiment.txt
```

此制表符分隔的文本檔案( [!DNL .txt])可位於 [!DNL Sensor] 資料夾，並且可以有任何方便的名稱。

確保記錄實驗目錄的位置和您指定的配置檔案的名稱，因為您需要使用此名稱和此目錄中保存實驗配置檔案（將在本指南稍後介紹）。

>[!NOTE]
>
>如果未在Web群集中的每台電腦上相同地設定此參數， [!DNL Sensor] 安裝，控制實驗不起作用。

此條目可以預配置並保留在 [!DNL Sensor] 不會造成任何負面影響。 如果未找到指定的實驗配置檔案名 [!DNL Sensor] 或者為空白（即存在但沒有內容）, [!DNL Sensor] 不進行實驗，在HTTP伺服器上記錄錯誤事件，並在所有其他方面繼續正常運行。
