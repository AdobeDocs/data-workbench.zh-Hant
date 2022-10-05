---
description: 將visual_sciences.dll添加到Tomcat java庫路徑的說明。
title: 修改 Java 程式庫路徑
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
exl-id: bd853d95-3f44-4860-9965-c3210ec4adcf
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 12%

---

# 修改 Java 程式庫路徑{#modify-the-java-library-path}

{{eol}}

將visual_sciences.dll添加到Tomcat java庫路徑的說明。

1. 在Windows伺服器上，導覽至Tomcat安裝目錄。 (Tomcat > bin)
1. 在bin資料夾下，運行Tomcat9w.exe（通用守護程式服務管理器）。

在Java頁簽的Java選項下，添加新行：

```
-Djava.library.path=C:\Sensor directory
```

其中C:\Sensor directory is the directory containing the visual_sciences.dll檔案。
