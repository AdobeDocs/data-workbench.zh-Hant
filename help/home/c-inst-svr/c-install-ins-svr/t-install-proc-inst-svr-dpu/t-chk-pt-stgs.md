---
description: 依預設，Insight Server會偵聽連接埠80（適用於HTTP）和443（適用於HTTPS）。
title: 檢查連接埠設定
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
exl-id: 924860e3-5afa-4c0f-bb7a-d38d5c1355b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 7%

---

# 檢查連接埠設定{#checking-the-port-settings}

{{eol}}

依預設，Insight Server會偵聽連接埠80（適用於HTTP）和443（適用於HTTPS）。

如果這些埠已由安裝的電腦上的其他進程分配 [!DNL Insight Server]，請使用下列程式來變更 [!DNL Insight Server’s] 埠分配。

**更改埠分配**

1. 導覽至 [!DNL Components] 資料夾（位於安裝的目錄中） [!DNL Insight Server].

   範例：[!DNL C:\Adobe\Server\Components]

1. 開啟 [!DNL Communications.cfg] 檔案（如記事本）。
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

1. 如果這些不是您想要的埠 [!DNL Insight Server] 要使用，請更改埠分配，然後保存並關閉檔案。
