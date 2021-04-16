---
description: Insight Server的用戶端(Report and Insight)使用通用名稱來參照Insight Server。
title: 定義伺服器的網路位置
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# 定義伺服器的網路位置{#defining-the-server-s-network-location}

Insight Server的用戶端(Report and Insight)使用通用名稱來參照Insight Server。

例如，當您將[!DNL Insight]或[!DNL Report]連接至[!DNL Insight Server]時，您會以其公用名稱來識別伺服器（例如[!DNL Server.MyCompany.com]）。 在內部，用戶端會先將公用名稱解析為數值IP位址，再傳送要求至伺服器。

要解析IP地址的常用名稱，[!DNL Insight Server’s]客戶端使用名為地址檔案的本地查找檔案。 地址檔案列出了在您的組織中安裝的[!DNL Insight Servers]的公用名稱，並標識其數字IP地址。 當客戶機在[!DNL Insight Server]上開啟配置檔案時，會自動接收地址檔案的副本。

當用戶端向[!DNL Insight Server]發出請求時，會嘗試透過位址檔案解析伺服器的通用名稱。 如果地址檔案標識所請求伺服器的IP地址，則客戶機將請求路由到指定地址。 如果未定義地址（例如，地址檔案未定義伺服器的公用名稱），請求就會失敗。 或者，您也可以設定用戶端，在用戶端的位址檔案中未定義名稱時，透過作業環境的一般網域命名服務(DNS)機制解析位址。 有關說明，請參見下節中[NetworkLocation參數表](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05)中的父參數。
