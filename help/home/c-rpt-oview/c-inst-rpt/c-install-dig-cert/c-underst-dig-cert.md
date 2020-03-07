---
description: Adobe使用X.509數位憑證來識別和驗證構成實作的用戶端和伺服器元件。
solution: Analytics
title: 瞭解數位憑證
topic: Data workbench
uuid: a2d84e9a-16aa-4973-85da-303614a4ad7f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 瞭解數位憑證{#understanding-digital-certificates}

Adobe使用X.509數位憑證來識別和驗證構成實作的用戶端和伺服器元件。

在安裝時， [!DNL Report Server]您必須安裝數位憑證，以授權指名的個人（例如Jane Smith）使用已安裝的用戶端應用程式。

>[!NOTE]
>
>如果您需要移轉至 [!DNL Report Server] 其他電腦或其他指名用戶，您必須從Adobe取得新的憑證。 若要這麼做，請聯絡Adobe客戶服務。

[!DNL Report Server] 提供此數位憑證以存取伺服器元件。 伺服器元件的管理員可以根據用戶端憑證中顯示的通用名稱或組織單位值，限制對伺服器資源的存取。

隨Adobe應用程式安裝的X.509數位憑證也可讓其用戶端和伺服器元件透過安全通訊端層(SSL)交換資訊。 SSL使用公開和私密金鑰加密系統，保護透過HTTP傳輸的安全。 Adobe的SSL實作支援1024位元RSA金鑰，並使用128位元RC4加密演算法。

除了安全性外，您安裝的數位憑證也可當成授權金鑰，讓您執行已安裝的憑證 [!DNL Report Server]。 若要正常運作，數位憑證必須是節點鎖定且為目前狀態，否則應用程式將無法啟動。

## 節點鎖定的證書 {#section-3338f1558e7844888dced8f395888744}

節點鎖定證書是已註冊到安裝該證書的電腦的數字證書。 節點鎖定將證書與特定節點標識符（唯一標識特定電腦的值）永久關聯。 若要節點鎖定憑證，您的電腦必須能夠透過網際網路存取Adobe授權伺服器或擁有授權伺服器存取權的代理伺服器。

如果您要安裝在無法存取網際網路的機器上，您必須依本頁「在無網際網路存取的機器上使用數位憑證」中所述，取得並安裝特殊的預先鎖定憑證 [](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-underst-dig-cert.md#section-18cce05e2204407bb2b6b75deab9197d) 。

如果您要安裝在可存取網際網路的機器上，您的數位憑證會在您第一次啟動時自動鎖定節點 [!DNL Report Server]。 在節點鎖定後，該證書無法用於任何其他電腦。 如果您需要移轉至 [!DNL Report Server] 另一部電腦，您必須從Adobe取得新的解除鎖定憑證。

## 目前憑證 {#section-b4053ab714514dfb97ea7f61bbb8da1e}

除了節點鎖定外，數位憑證必須是最新的。 若要保持最新狀態，您的憑證必須定期重新驗證（通常每30天重新驗證一次，但視您與Adobe的合約而定）。 如果您的電腦可以存取網際網路，重新驗證程式會完全透明。 [!DNL Report Server] 會自動連線至授權伺服器，並視需要重新驗證憑證。 如果您的電腦沒有網際網路存取權，您必須依照下節所述手動安裝更新的憑證。

## 在無網際網路存取的電腦上使用數位憑證 {#section-18cce05e2204407bb2b6b75deab9197d}

如果要安裝在無法訪問Internet的電腦上，則必須為安裝請求預鎖定的證書 [!DNL Report Server]。 預先鎖定的憑證是Adobe手動鎖定至機器節點識別碼的數位憑證。

若要要求預先鎖定的憑證，您必須傳送節點識別碼和憑證編號給Adobe客戶服務。 若要取得您電腦的節點識別碼，請聯絡Adobe客戶服務以要求Adobe公用程 [!DNL Node Identifier] 式。 您也可以從警報中取得節點識別碼，當 [!DNL Report Server] 它嘗試連線至授權伺服器時，會發生問題，但無法。 當您收到預先鎖定的憑證時，請依照數位憑證安裝程式的最後兩個步驟 [中所述進行安裝](../../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/t-dig-cert-install-proc.md#task-5c4bb352ff534b40adc46dd053874e5d)。

當需要重新驗證憑證時，您必須從授權伺服器下載新的已驗證憑證，然後在您的電腦上重新安裝（除非您與Adobe另有協定）。
