---
description: 安裝及設定報表伺服器軟體的步驟。
title: 安裝概述
uuid: ffc72aa1-98d8-41dc-b4e5-6f70ff43430e
exl-id: 4ddc0761-a999-49ed-b0e4-12cf34e2688c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 2%

---

# 安裝概述{#installation-overview}

安裝及設定報表伺服器軟體的步驟。

必須按順序完成以下任務：

1. 安裝報告伺服器程式檔案。
1. 下載並安裝Report Server數位憑證。 請參閱[下載和安裝數位憑證](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)。
1. 設定報表伺服器與資料工作台伺服器(InsightServer64.exe)之間的連線。 請參閱[設定Insight Server的連線](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c)。
1. 使用語言檔案（.zbin檔案）更新報表伺服器。

   請參閱[使用語言檔案（.zbin檔案）](../../../home/c-rpt-oview/c-inst-rpt/c-zbin-file-update.md#concept-5637a8f52b7643759e423c2068b4126b)更新報表伺服器。 1.更新資料工作台伺服器機器上的存取控制檔案，讓報表伺服器可存取資料工作台伺服器。 請參閱[啟用Insight Server的存取權](../../../home/c-rpt-oview/c-inst-rpt/t-en-acc-ins-svr.md#task-e7b95cf9cb194842ad72fa534c56c3cc)。
1. 編輯主資料工作台伺服器機器上的通訊檔案，以在[!DNL Master Server Detailed Status]介面中顯示報表伺服器的狀態。 請參閱[設定Insight伺服器以顯示報表的伺服器狀態](../../../home/c-rpt-oview/c-inst-rpt/t-display-svr-st-rpt.md#task-a14d096f85924d9b93eef950591f93a8)。
1. 將報表註冊為Windows服務。 請參閱[將報表註冊為Windows服務](../../../home/c-rpt-oview/c-inst-rpt/t-reg-rpt-win-svc.md#task-a8762d7818ed4cfd87e616db6a68b3a6)。
