---
description: Insight Server的用戶端(Report & Insight)使用通用名稱來指稱Insight Server。
title: 定義伺服器的網路位置
uuid: 9cf2f268-6fde-4427-b832-a238d126d697
exl-id: def360b8-f146-45ca-ae61-fd213adef68b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 4%

---

# 定義伺服器的網路位置{#defining-the-server-s-network-location}

{{eol}}

Insight Server的用戶端(Report &amp; Insight)使用通用名稱來指稱Insight Server。

例如，當您連線 [!DNL Insight] 或 [!DNL Report] 到 [!DNL Insight Server]，您可依其共同名稱來識別伺服器(例如 [!DNL Server.MyCompany.com])。 在內部，用戶端先將通用名稱解析為數值IP位址，再傳送要求給伺服器。

若要將一般名稱解析為IP位址， [!DNL Insight Server’s] 用戶端會使用名為「位址檔案」的本機查詢檔案。 地址檔案列出 [!DNL Insight Servers] 安裝，並識別其數值IP位址。 用戶端在 [!DNL Insight Server].

當用戶端向 [!DNL Insight Server]，會嘗試透過位址檔案解析伺服器的通用名稱。 如果地址檔案標識所請求伺服器的IP地址，則客戶端將請求路由到指定地址。 如果地址未定義（例如，地址檔案未定義伺服器的公用名稱），則請求失敗。 您可以選擇配置客戶端，在客戶端的地址檔案中未定義名稱時，通過操作環境的正常域命名服務(DNS)機制解析地址。 如需指示，請參閱 [網路位置參數表](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-ntwk-loc.md#concept-18587827cbd24805801caa86bc816e05) ，於下節。
