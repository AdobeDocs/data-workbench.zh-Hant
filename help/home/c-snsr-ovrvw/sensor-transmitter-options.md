---
description: 有關UNIX和Windows的感測器發射器啟動命令的資訊。
title: 感測器發射器命令行選項
uuid: 8d077d76-a709-494e-a176-07ca3e761662
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 感測器發射器命令行選項{#sensor-transmitter-command-line-options}

有關UNIX和Windows的感測器發射器啟動命令的資訊。

## UNIX的啟動命令 {#section-e8e7a6e62971499ba5f633d896590949}

要在UNIX幹部上啟動感測器發射器，請使用以下命令：

```
txlogd -f configFileName
```

其中configFileName是發射器配置檔案(txlogd.conf)的完全限定名稱。

預設情況下，發射器作為後台進程（守護程式）運行，並將操作消息寫入syslog。

以下是txlogd命令行開關的完整清單：

| 交換機 | 說明 |
|---|---|
| -f | 指定配置檔案(txlogd.conf)的完全限定名稱。 如果未指定此開關，則發射器在當前目錄中查找txlogd.conf。 |
| -n | 以互動模式啟動發射器（而非作為背景處理）。 |
| -i | 以互動模式啟動傳送器，並將除錯輸出導向至stdout。 |
| -d | 以後台進程啟動發射器，並將調試輸出定向到當前目錄中的txlogd-debug.log。 |
| -c | 啟動發射器並建立磁碟佇列檔案（如果不存在）。 如果磁碟隊列已存在，則忽略此參數。 |
| -x | 啟動發射器，並在它發送磁碟隊列中的最後一個資料包後使其退出。 您可以使用此選項來排出隊列，以準備管理操作，例如建立新隊列檔案。 |

## Windows版啟動命令 {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

要啟動感測器並將其註冊為Windows系統上的服務，請使用以下命令：

```
txlog /regserver
```

