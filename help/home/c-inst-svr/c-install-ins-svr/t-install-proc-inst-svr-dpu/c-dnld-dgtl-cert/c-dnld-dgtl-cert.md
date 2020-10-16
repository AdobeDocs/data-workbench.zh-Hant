---
description: 數位憑證的一般資訊，以及下載和安裝數位憑證的程序。
solution: Analytics
title: 下載和安裝數位憑證
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: ht
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: ht
source-wordcount: '916'
ht-degree: 100%

---


# 下載和安裝數位憑證{#downloading-and-installing-the-digital-certificates}

數位憑證的一般資訊，以及下載和安裝數位憑證的程序。

* [了解數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [節點鎖定憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [最新憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [在無法存取網際網路的電腦上使用數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [數位憑證安裝程序](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## 了解數位憑證 {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe 使用 X.509 數位憑證來識別和驗證實作的用戶端和伺服器元件。

安裝伺服器元件 ([!DNL Insight Server] 或 [!DNL Repeater]) 時，您必須安裝 Adobe 為元件核發的數位憑證。如果您需要將 Adobe 應用程式移轉至其他電腦，必須向 Adobe 取得新憑證。若要取得新憑證，請連絡 Adobe 客戶服務。

此憑證上顯示的一般名稱會依指定的網域名稱 (例如 [!DNL vs001a.mycompany.com]) 識別伺服器。伺服器用戶端連線至此伺服器時，伺服器會提供此憑證，以證明它確實是該用戶端要求的伺服器。

同樣地，安裝伺服器用戶端 (例如 [!DNL Insight] 或 [!DNL Report]) 時，您必須安裝數位憑證，授權指名的人員 (例如 Jane Smith) 使用安裝的用戶端應用程式。如果您需要將 Adobe 應用程式移轉至其他電腦或其他指名使用者，必須向 Adobe 取得新憑證。若要取得新憑證，請連絡 Adobe 客戶服務。

用戶端應用程式會提供此數位憑證，以存取伺服器元件。伺服器元件的管理員可以根據用戶端憑證中顯示的一般名稱或組織單位值，限制存取伺服器資源。

與 Adobe 應用程式一併安裝的 X.509 數位憑證也可讓其用戶端和伺服器元件透過安全通訊端層 (SSL) 交換資訊。SSL 使用公開和私密金鑰加密系統，透過 HTTP 保護傳輸安全。Adobe 的 SSL 實作支援 1024 位元 RSA 金鑰，並使用 128 位元 RC4 加密演算法。

除了安全性外，您安裝的數位憑證也可當成授權金鑰，讓您執行已安裝的 Adobe 軟體。若要正常運作，數位憑證必須為節點鎖定且最新，否則應用程式不會啟動。

## 字串加密 {#section-8abe6b2d95704d38a04137d5c4602f0b}

如需加密密碼，請參閱[字串加密](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a)。

## 節點鎖定憑證 {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

節點鎖定憑證是已註冊到安裝該憑證之電腦的數位憑證。節點鎖定會將憑證與特定節點識別碼 (專屬識別特定電腦的值) 建立永久關聯。若要節點鎖定憑證，您的電腦必須能夠透過網際網路存取 Adobe License Server，或是存取可存取 License Server 的代理伺服器。

如果您要在無法存取網際網路的電腦上進行安裝，必須如[在無法存取網際網路的電腦上使用數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)中所述，取得並安裝特殊的預先鎖定憑證。

如果您要在可存取網際網路的電腦上進行安裝，您的數位憑證會在您第一次啟動 Adobe 產品時自動與節點鎖定。在與節點鎖定後，該憑證就無法用於任何其他電腦。如果您需要將 Adobe 產品移轉至其他電腦，必須向 Adobe 取得新的解除鎖定憑證。

## 最新憑證 {#section-15aabaa8625c46edaa7436e1f3fc29c5}

除了節點鎖定外，數位憑證必須為最新。若要保持最新狀態，您的憑證必須定期重新驗證 (通常每 30 天一次，但可視您與 Adobe 的合約而定)。如果您的電腦可存取網際網路，重新驗證程序會完全透明。您的 Adobe 產品會自動連線至 License Server，並在必要時重新驗證憑證。如果您的電腦無法存取網際網路，則必須依照下節所述手動安裝更新的憑證。

## 在無法存取網際網路的電腦上使用數位憑證 {#section-809366329a7d4e198f95fe06c1f534fa}

如果您要在無法存取網際網路的電腦上進行安裝，必須索取預先鎖定憑證，才能安裝 [!DNL Insight Server]。預先鎖定憑證是 Adobe 手動鎖定至電腦節點識別碼的數位憑證。

若要索取預先鎖定憑證，您必須傳送節點識別碼和憑證編號給 Adobe 客戶服務。若要取得您電腦的節點識別碼，請向 Adobe 客戶服務要求 Adobe Node Identifier 公用程式。您也可以在 Adobe 軟體嘗試連線至 License Server 但失敗時發出的警報中取得節點識別碼。

收到預先鎖定憑證時，請依照[數位憑證安裝程序](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)的最後兩個步驟所述進行安裝。需要重新驗證憑證時，您必須從 License Server 下載經過驗證的新憑證，然後在您的電腦上重新安裝。

## 數位憑證安裝程序 {#section-19f31676aad344a98e26e4fca1fad03b}

**若要下載及安裝數位憑證**

1. 開啟網路瀏覽器，前往 [https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >您的瀏覽器可能會在這時提示您提供數位憑證。如果出現提示，按一下「**[!UICONTROL Cancel]**」即可關閉對話方塊。

1. 在登入畫面中，輸入 Adobe 提供的「**[!UICONTROL Account Name]**」和「**[!UICONTROL Password]**」，然後按一下「**[!UICONTROL login]**」。

1. 找到已為您的 [!DNL Insight Server] 核發的憑證，然後按一下與該憑證關聯的圖示。

   >[!NOTE]
   >
   >記下指派給此憑證的一般名稱。您會在稍後的步驟中使用此名稱。

1. 提示儲存憑證時，請按一下「**[!UICONTROL Save]**」。(請注意，檔案名稱會符合與憑證相關聯的一般名稱。)
1. 將檔案下載至「[!DNL Insight Server]」安裝目錄中的「[!DNL Certificates]」檔案夾。此檔案夾已有憑證檔案「[!DNL trust_ca_cert.pem]」。這是不可或缺的憑證檔案。

1. 將下載的憑證檔案重新命名為：

[!DNL server_cert.pem]

