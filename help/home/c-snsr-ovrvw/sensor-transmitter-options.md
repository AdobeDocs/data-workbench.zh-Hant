---
description: 有關UNIX和Windows的Sensor傳輸器啟動命令的資訊。
title: Sensor 傳送器命令列選項
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 6%

---

# Sensor 傳送器命令列選項{#sensor-transmitter-command-line-options}

{{eol}}

有關UNIX和Windows的Sensor傳輸器啟動命令的資訊。

## UNIX的啟動命令 {#section-e8e7a6e62971499ba5f633d896590949}

要在UNIX幹線上啟動Sensor傳輸器，請使用以下命令：

```
txlogd -f configFileName
```

其中configFileName是傳輸器組態檔(txlogd.conf)的完全限定名稱。

預設情況下，發射器作為後台進程（守護程式）運行，並將操作消息寫入syslog。

以下是txlogd的命令行開關的完整清單：

| 交換機 | 說明 |
|---|---|
| -f | 指定設定檔案(txlogd.conf)的完全限定名稱。 如果您未指定此開關，傳送器會在目前目錄中尋找txlogd.conf。 |
| -n | 以互動式模式啟動傳送器（而非背景程式）。 |
| -i | 以互動式模式啟動傳送器，並將除錯輸出導向至stdout。 |
| -d | 以背景程式啟動傳送器，並將除錯輸出導向目前目錄中的txlogd-debug.log。 |
| -c | 啟動發送器，並建立磁碟隊列檔案（如果不存在）。 如果磁碟隊列已存在，則忽略此參數。 |
| -x | 啟動發送器，並在它發送磁碟隊列中的最後一個資料包後，使其退出。 您可以使用此選項來排空佇列，以準備管理操作，例如建立新的佇列檔案。 |

## Windows的啟動命令 {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

要啟動Sensor並在Windows系統上將其註冊為服務，請使用以下命令：

```
txlog /regserver
```
