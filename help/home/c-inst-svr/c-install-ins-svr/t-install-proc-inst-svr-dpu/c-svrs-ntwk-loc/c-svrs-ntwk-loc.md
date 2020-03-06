---
description: Insight Server的用戶端(Report and Insight)使用通用名稱來參照Insight Server。
solution: Insight
title: 定義伺服器的網路位置
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 定義伺服器的網路位置{#defining-the-server-s-network-location}

Insight Server的用戶端(Report and Insight)使用通用名稱來參照Insight Server。

例如，當您連接或連 [!DNL Insight] 接至 [!DNL Report] 某 [!DNL Insight Server]個伺服器時，可通過其公用名稱(例如， [!DNL Server.MyCompany.com])來標識該伺服器。 在內部，用戶端會先將公用名稱解析為數值IP位址，再傳送要求至伺服器。

要將常見名稱解析為IP地址， [!DNL Insight Server’s] 客戶端使用名為地址檔案的本地查找檔案。 地址檔案列出在您的組織中安 [!DNL Insight Servers] 裝的通用名稱，並標識其數字IP地址。 當客戶機在上開啟配置檔案時，會自動接收地址檔案的副本 [!DNL Insight Server]。

當用戶端向某個用戶端發出 [!DNL Insight Server]要求時，會嘗試透過位址檔案解析伺服器的通用名稱。 如果地址檔案標識所請求伺服器的IP地址，則客戶機將請求路由到指定地址。 如果未定義地址（例如，地址檔案未定義伺服器的公用名稱），請求就會失敗。 或者，您也可以設定用戶端，在用戶端的位址檔案中未定義名稱時，透過作業環境的一般網域命名服務(DNS)機制解析位址。 有關說明，請參閱下節「網路位置參 [數」(NetworkLocation Parameters](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) )表格中的父參數。
