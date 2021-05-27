---
description: 依預設，Insight Server會偵聽連接埠80（適用於HTTP）和443（適用於HTTPS）。
title: 檢查連接埠設定
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# 檢查連接埠設定{#checking-the-port-settings}

依預設，Insight Server會偵聽連接埠80（適用於HTTP）和443（適用於HTTPS）。

如果這些埠已由安裝了[!DNL Insight Server]的電腦上的其他進程分配，請使用以下過程更改[!DNL Insight Server’s]埠分配。

**更改埠分配**

1. 導覽至[!DNL Insight Server]安裝目錄中的[!DNL Components]資料夾。

   範例：[!DNL C:\Adobe\Server\Components]

1. 在文本編輯器（如記事本）中開啟[!DNL Communications.cfg]檔案。
1. 找到埠和SSL埠條目，如下所示：

   ```
   component = CommServer: 
     Access Control File = Path: Access Control\\Access Control.cfg
     Access Log Directory = string: P:\\Audit\\
     IP Interface = string: 
     Port = int: 80
     SSL Port = int: 443
     Servers = vector: 17 items
       0 = InitServer: 
         Client Type = string: Sensor
         URI = string: /SensorInit.vsp
     . . .
   ```

1. 如果這些埠不是您希望[!DNL Insight Server]使用的埠，請更改埠分配，然後保存並關閉該檔案。
