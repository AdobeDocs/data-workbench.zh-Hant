---
description: 有關將visual_sciences.dll添加到Tomcat Java庫路徑的說明。
title: 修改Java庫路徑
uuid: 1e1a2704-045a-4b35-aa43-1b5bae91dc32
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 修改Java庫路徑{#modify-the-java-library-path}

有關將visual_sciences.dll添加到Tomcat Java庫路徑的說明。

1. 在您的Windows伺服器上，導覽至Tomcat安裝目錄。 (Tomcat > bin)
1. 在bin資料夾下，運行Tomcat9w.exe（常用守護程式服務管理器）。

在「Java」頁籤的「Java選項」下，添加新行：

```
-Djava.library.path=C:\Sensor directory
```

其中C:\Sensor directory is the directory containing the visual_sciences.dll檔案。
