---
description: ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。
solution: Analytics
title: 修改 ExpFile 參數
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# 修改 ExpFile 參數{#modifying-the-expfile-parameter}

{{eol}}

ExpFile參數指向實驗配置檔案的位置，該檔案定義了實驗。

設定此參數可讓您執行實驗。 如需建立實驗設定檔案的步驟，請參閱 [設定和部署實驗](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

以下是ExpFile參數的範例：

```
ExpFile /home/experiment.txt
```

此定位點分隔的文字檔案( [!DNL .txt])可位於 [!DNL Sensor] 檔案夾和可以有任何方便的名稱。

請務必記錄實驗目錄的位置以及您指定的配置檔案的名稱，因為您需要使用此名稱和此目錄中保存實驗配置檔案（將在本指南稍後介紹）。

>[!NOTE]
>
>如果您未在Web叢集中， [!DNL Sensor] 已安裝，受控實驗無法運作。

此項目可預先設定，並保留在 [!DNL Sensor] 持續配置檔案，無不良影響。 如果找不到指定的實驗配置檔案名 [!DNL Sensor] 或空白（即存在，但無內容）, [!DNL Sensor] 不會進行實驗、在HTTP伺服器上記錄錯誤事件，且會在所有其他方面繼續正常運作。
