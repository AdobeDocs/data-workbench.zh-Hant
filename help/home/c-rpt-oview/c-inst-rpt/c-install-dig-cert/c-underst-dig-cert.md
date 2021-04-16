---
description: Adobe 使用 X.509 數位憑證來識別和驗證實作的用戶端和伺服器元件。
title: 了解數位憑證
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
exl-id: 967e9d5b-7972-497e-8902-8db0eb304f27
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 54%

---

# 了解數位憑證{#understanding-digital-certificates}

Adobe 使用 X.509 數位憑證來識別和驗證實作的用戶端和伺服器元件。

當您安裝[!DNL Report Server]時，必須安裝數位憑證，以授權指名的個人（例如Jane Smith）使用已安裝的用戶端應用程式。

>[!NOTE]
>
>如果您需要將[!DNL Report Server]遷移到另一台電腦或另一個指名用戶，則必須從Adobe獲取新證書。 若要取得新憑證，請連絡 Adobe 客戶服務。

[!DNL Report Server] 提供此數位憑證以存取伺服器元件。伺服器元件的管理員可以根據用戶端憑證中顯示的一般名稱或組織單位值，限制存取伺服器資源。

與 Adobe 應用程式一併安裝的 X.509 數位憑證也可讓其用戶端和伺服器元件透過安全通訊端層 (SSL) 交換資訊。SSL 使用公開和私密金鑰加密系統，透過 HTTP 保護傳輸安全。Adobe 的 SSL 實作支援 1024 位元 RSA 金鑰，並使用 128 位元 RC4 加密演算法。

除了安全性外，您安裝的數位憑證也可當成授權金鑰，讓您執行已安裝的[!DNL Report Server]。 若要正常運作，數位憑證必須是節點鎖定且為目前狀態，否則應用程式將無法啟動。

## 節點鎖定憑證 {#section-3338f1558e7844888dced8f395888744}

節點鎖定憑證是已註冊到安裝該憑證之電腦的數位憑證。節點鎖定會將憑證與特定節點識別碼 (專屬識別特定電腦的值) 建立永久關聯。若要節點鎖定憑證，您的電腦必須能夠透過網際網路存取 Adobe License Server，或是存取可存取 License Server 的代理伺服器。

如果要安裝在無法訪問Internet的電腦上，則必須獲得並安裝特殊的預鎖定證書，如本頁的「在沒有Internet訪問的電腦上使用數字證書」中所述。[](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d)

如果您要安裝在可存取網際網路的機器上，您的數位憑證會在您第一次啟動[!DNL Report Server]時自動被節點鎖定。 在與節點鎖定後，該憑證就無法用於任何其他電腦。如果您需要將[!DNL Report Server]遷移到另一台電腦，則必須從Adobe獲得一個新的解鎖證書。

## 最新憑證 {#section-b4053ab714514dfb97ea7f61bbb8da1e}

除了節點鎖定外，數位憑證必須為最新。若要保持最新狀態，您的憑證必須定期重新驗證(通常每30天，但視您與Adobe的合約而定)。 如果您的電腦可存取網際網路，重新驗證程序會完全透明。[!DNL Report Server] 會自動連線至授權伺服器，並視需要重新驗證憑證。如果您的電腦無法存取網際網路，則必須依照下節所述手動安裝更新的憑證。

## 在無法存取網際網路的電腦上使用數位憑證 {#section-18cce05e2204407bb2b6b75deab9197d}

如果您要在無法存取網際網路的電腦上進行安裝，必須索取預先鎖定憑證，才能安裝 [!DNL Report Server]。預先鎖定憑證是 Adobe 手動鎖定至電腦節點識別碼的數位憑證。

若要索取預先鎖定憑證，您必須傳送節點識別碼和憑證編號給 Adobe 客戶服務。要獲取電腦的節點標識符，請與Adobe客戶服務聯繫以請求Adobe[!DNL Node Identifier]實用程式。 您也可以從[!DNL Report Server]嘗試連線至授權伺服器且無法連線時發出的警報中取得節點識別碼。 收到預先鎖定憑證時，請依照[數位憑證安裝程序](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d)的最後兩個步驟所述進行安裝。

當需要重新驗證憑證時，您必須從授權伺服器下載新的已驗證憑證，然後將它重新安裝在您的電腦上(除非您同意Adobe狀態)。
