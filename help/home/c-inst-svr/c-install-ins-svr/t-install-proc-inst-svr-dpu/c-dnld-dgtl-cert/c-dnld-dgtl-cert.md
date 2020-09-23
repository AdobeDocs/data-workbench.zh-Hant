---
description: 有關數位憑證的一般資訊，以及下載和安裝這些憑證的程式。
solution: Analytics
title: 下載和安裝數位憑證
uuid: ac484e96-21dc-4643-ae74-01ac957e30ee
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 3%

---


# 下載和安裝數位憑證{#downloading-and-installing-the-digital-certificates}

有關數位憑證的一般資訊，以及下載和安裝這些憑證的程式。

* [瞭解數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-e48a776ef39042759d1dfb3444996d8b)
* [節點鎖定的證書](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-b3dc7dcf2aa3439cbe66b0461b42d485)
* [目前憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-15aabaa8625c46edaa7436e1f3fc29c5)
* [在無網際網路存取的電腦上使用數位憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)
* [數位憑證安裝程序](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)

## 瞭解數位憑證 {#section-e48a776ef39042759d1dfb3444996d8b}

Adobe使用X.509數位憑證來識別和驗證構成實作的用戶端和伺服器元件。

當您安裝伺服器元件( [!DNL Insight Server] 或 [!DNL Repeater])時，您必須安裝Adobe為元件核發的數位憑證。 如果您需要將Adobe應用程式移轉至其他機器，您必須從Adobe取得新的憑證。 若要這麼做，請聯絡Adobe客戶服務。

此證書上顯示的公用名稱通過指定的域名(例如 [!DNL vs001a.mycompany.com])標識伺服器。 當伺服器用戶端連線至此伺服器時，伺服器會提供此憑證，以證明它確實是該用戶端所要求的伺服器。

同樣地，當您安裝伺服器用戶端(例如 [!DNL Insight] 或 [!DNL Report])時，您必須安裝數位憑證，以授權指名的個人（例如Jane Smith）使用所安裝的用戶端應用程式。 如果您需要將Adobe應用程式移轉至其他電腦或其他指名用戶，您必須從Adobe取得新的憑證。 若要這麼做，請聯絡Adobe客戶服務。

客戶端應用程式提供此數字證書以獲得對伺服器元件的訪問。 伺服器元件的管理員可以根據用戶端憑證中顯示的通用名稱或組織單位值，限制對伺服器資源的存取。

隨Adobe應用程式安裝的X.509數位憑證也可讓其用戶端和伺服器元件透過安全通訊端層(SSL)交換資訊。 SSL使用公開和私密金鑰加密系統，保護透過HTTP傳輸的安全。 Adobe的SSL實作支援1024位元RSA金鑰，並使用128位元RC4加密演算法。

除了安全性外，您安裝的數位憑證也可當成授權金鑰，讓您執行已安裝的Adobe軟體。 若要正常運作，數位憑證必須是節點鎖定且為目前狀態，否則應用程式不會啟動。

## 字串加密 {#section-8abe6b2d95704d38a04137d5c4602f0b}

請參 [閱字串加密](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/string-encryption.md#concept-35da0b53650a4d7e82b240ad27f6d45a) ，以取得密碼加密。

## 節點鎖定的證書 {#section-b3dc7dcf2aa3439cbe66b0461b42d485}

節點鎖定證書是已註冊到安裝該證書的電腦的數字證書。 節點鎖定將證書與特定節點標識符（唯一標識特定電腦的值）永久關聯。 若要節點鎖定憑證，您的電腦必須能夠透過網際網路存取Adobe License Server，或是存取授權伺服器的代理伺服器。

如果您要安裝在無法存取網際網路的機器上，您必須依照在無網際網路存取的機器上使用數位憑證，取得並安裝特殊的 [預先鎖定憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-809366329a7d4e198f95fe06c1f534fa)。

如果您要安裝在可存取網際網路的機器上，您的數位憑證會在您第一次啟動Adobe產品時自動鎖定節點。 在節點鎖定後，該證書無法用於任何其他電腦。 如果您需要將Adobe產品移轉至其他電腦，您必須從Adobe取得新的解除鎖定憑證。

## 目前憑證 {#section-15aabaa8625c46edaa7436e1f3fc29c5}

除了節點鎖定外，數位憑證必須是最新的。 若要保持最新狀態，您的憑證必須定期重新驗證（通常每30天重新驗證一次，但視您與Adobe的合約而定）。 如果您的電腦可以存取網際網路，重新驗證程式會完全透明。 您的Adobe產品會自動連線至授權伺服器，並在有需要時重新驗證憑證。 如果您的電腦沒有網際網路存取權，您必須依照下節所述手動安裝更新的憑證。

## 在無網際網路存取的電腦上使用數位憑證 {#section-809366329a7d4e198f95fe06c1f534fa}

如果要安裝在無法訪問Internet的電腦上，則必須為安裝請求預鎖定的證書 [!DNL Insight Server]。 預先鎖定的憑證是Adobe手動鎖定至機器節點識別碼的數位憑證。

若要要求預先鎖定的憑證，您必須傳送節點識別碼和憑證編號給Adobe客戶服務。 若要取得您電腦的節點識別碼，請聯絡Adobe客戶服務以要求Adobe節點識別碼公用程式。 您也可以從Adobe軟體嘗試連線至授權伺服器而無法連線時發出的警報中取得節點識別碼。

當您收到預先鎖定的憑證時，請依照數位憑證安裝程式的最後兩個步驟 [中所述進行安裝](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#section-19f31676aad344a98e26e4fca1fad03b)。 當需要重新驗證憑證時，您必須從授權伺服器下載新的已驗證憑證，然後在您的電腦上重新安裝。

## 數位憑證安裝程序 {#section-19f31676aad344a98e26e4fca1fad03b}

**下載並安裝數位憑證**

1. 開啟您的網頁瀏覽器至 [https://aap.adobe.com](https://aap.adobe.com)。

   >[!NOTE]
   >
   >您的瀏覽器可能會提示您目前呈現數位憑證。 如果出現，只需按一 **[!UICONTROL Cancel]** 下以關閉對話方塊。

1. 在登入畫面中，輸入您 **[!UICONTROL Account Name]** 從Adobe收 **[!UICONTROL Password]** 到的和，然後按一下 **[!UICONTROL login]**。

1. 找出已為您核發的憑證， [!DNL Insight Server]然後按一下與該憑證關聯的圖示。

   >[!NOTE]
   >
   >記下指派給此證書的公用名稱。 您在稍後的步驟中使用此名稱。

1. 當提示儲存憑證時，按一下 **[!UICONTROL Save]**。 （請注意，檔案名稱與憑證相關的公用名稱相符。）
1. 將檔案下載 [!DNL Certificates] 至您所安裝目錄的檔案夾 [!DNL Insight Server]。 此資料夾已包含名為的證書檔案 [!DNL trust_ca_cert.pem]。 此證書檔案必須始終存在。

1. 將下載的證書檔案更名為：

[!DNL server_cert.pem]

