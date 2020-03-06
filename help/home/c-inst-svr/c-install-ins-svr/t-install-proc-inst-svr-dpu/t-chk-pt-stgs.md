---
description: 依預設，Insight Server會監聽埠80（針對HTTP）和443（針對HTTPS）。
solution: Insight
title: 檢查埠設定
uuid: 1adad226-5891-4498-80b6-1bb4d67f5bbb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 檢查埠設定{#checking-the-port-settings}

依預設，Insight Server會監聽埠80（針對HTTP）和443（針對HTTPS）。

如果這些埠已經由已安裝的電腦上的其他進程分配 [!DNL Insight Server]，請按下列步驟更改埠 [!DNL Insight Server’s] 分配。

**要更改埠分配，請執行以下操作：**

1. 導覽至您 [!DNL Components] 所安裝目錄中的資料夾 [!DNL Insight Server]。

   範例: [!DNL C:\Adobe\Server\Components]

1. 在文本編 [!DNL Communications.cfg] 輯器（如記事本）中開啟檔案。
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

1. 如果這些埠不是您要使用的端 [!DNL Insight Server] 口，請更改埠分配，然後保存並關閉檔案。
