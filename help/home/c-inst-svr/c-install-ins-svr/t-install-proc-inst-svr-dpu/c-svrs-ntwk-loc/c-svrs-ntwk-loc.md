---
description: Insight Server的用戶端(Report & Insight)使用通用名稱來指稱Insight Server。
title: 定義伺服器的網路位置
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# 定義伺服器的網路位置{#defining-the-server-s-network-location}

Insight Server的用戶端(Report &amp; Insight)使用通用名稱來指稱Insight Server。

例如，當您將[!DNL Insight]或[!DNL Report]連接到[!DNL Insight Server]時，可以通過該伺服器的公用名稱（例如[!DNL Server.MyCompany.com]）來標識該伺服器。 在內部，用戶端先將通用名稱解析為數值IP位址，再傳送要求給伺服器。

要將常見名稱解析為IP地址，[!DNL Insight Server’s]客戶端使用名為地址檔案的本地查找檔案。 地址檔案列出在貴組織安裝的[!DNL Insight Servers]的常見名稱，並標識其數字IP地址。 客戶端在[!DNL Insight Server]上開啟配置檔案時自動接收地址檔案的副本。

當客戶端向[!DNL Insight Server]發出請求時，它會嘗試通過地址檔案解析伺服器的通用名稱。 如果地址檔案標識所請求伺服器的IP地址，則客戶端將請求路由到指定地址。 如果地址未定義（例如，地址檔案未定義伺服器的公用名稱），則請求失敗。 您可以選擇配置客戶端，在客戶端的地址檔案中未定義名稱時，通過操作環境的正常域命名服務(DNS)機制解析地址。 有關說明，請參閱以下部分[NetworkLocation參數表](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05)中的父參數。
