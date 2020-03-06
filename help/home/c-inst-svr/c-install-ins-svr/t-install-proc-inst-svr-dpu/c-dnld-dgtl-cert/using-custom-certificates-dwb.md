---
description: 使用自訂憑證的指示。
title: 在資料工作台中使用自訂憑證
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# 在資料工作台中使用自訂憑證{#using-custom-certificates-in-data-workbench}

使用自訂憑證的指示。

資料工作台用戶端或伺服器所使用的憑證必須由受信任的CA（認證授權機構）簽署。 資料工作台客戶會收到由Visual Sciences CA簽署的憑證。 這些憑證受Data Workbench軟體信任，因為 [!DNL trust_ca_cert.pem] (隨附於Insight軟體，並儲存在伺服器和用戶端的 **Certificates** directory)包含 *Visual Sciences CA的* Root CA Certificate。 當用戶端和伺服器使用SSL通訊時，這些憑證會用於軟體授權和驗證。 只有Visual Sciences CA核發的憑證才能用於授權，但其他憑證則可用於通訊和驗證。 CA（非Visual Sciences）核發的證書稱為自 *訂證書。*

**重要注意事項：** 對於伺服器和客戶機，資料工作台軟體使用安裝在客戶機或伺服器的證書目錄中的證書檔案 **** ，或配置中明確標識的證書。 不過，您也可以使用 [Windows Certificate Store](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) for clients。

以下說明使用自訂憑證在資料工作台用戶端與伺服器間通訊時應遵循的程式。 並非每個細節都是一項艱巨的要求，而且可以採用不同的過程變化。 不過，下列程式已經過測試，可正常運作。

## 設定自訂用戶端憑證 {#section-2083fd41973e451fa404e7a4ae4da591}

1. 將發證CA的證書添加到 [!DNL trust_cert_ca.pem]，該證書安裝在客戶機的 **Certificates** 目錄中，並且安裝在每個群集中要使用此自定義證書訪問的每個伺服器的證書目錄中。

1. 為群集中的每台伺服器獲取自定義證書，條件如下：

   1. 證書的格式為證 [!DNL .pem] 書。
   1. 憑證包含其金鑰且未加密（亦即不含密碼／密碼片語）。

      憑證包含其金鑰，其行如下：

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      從證書中刪除密碼短語的一種方 [!DNL .pem] 法：

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. 證書具有CN、O、OU等。 伺服器檔案中此客戶端的必 [!DNL Access Control.cfg] 要。
   1. 憑證的核發目的是*** *客戶端(或同時為客戶端（或同時為客戶端）的***** (或同時為客戶端（或同時為客戶端）或／或同時為客戶端(或同 *時為客戶端（或同時為Client）/Client(或同時為Client（或Client）))))的核發*********&#x200B;核發證的核證。

      要驗證證書是否具有伺服器和／或客戶機的目的代碼，可使用以下命令：

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      對於伺服器證書，兩個命令都應產生：

      ```
      custom_communications_cert.pem: OK
      ```

      對於客戶端證書，只需要第二個命令才能返回 [!DNL OK]。

1. 將證書放在客戶機的「證 **書** 」目錄中。
1. 在 [!DNL Insight.cfg] 您要 *使用此憑證的每個叢集的serverInfo下，請確定自訂用戶* 端憑證已命名 ** ，例如：

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## 設定自訂伺服器憑證 {#setting-up-custom-server-certificates}

本節假定您有一個群集正在啟動並運行，使用Visual Sciences頒發的證書，並且配置遵循常見做法(如主版上的 *Components for Processing Servers* directory將同步到所有DPU的 *Components* 目錄)。

1. 將發證CA的證書添加到群集中 [!DNL trust_cert_ca.pem] 每個伺服器上安裝的證書以及需要與此群集通信的每個客戶端。
1. 為群集中的每台伺服器獲取自定義證書，這些證書具有以下要求：

   1. 自訂憑證的格式為憑 [!DNL .pem] 證。
   1. 憑證包含其金鑰且未加密（亦即不含密碼／密碼片語）。

      如果證書有如下行，則證書包含其密鑰：

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      從證書中刪除密碼短語的一種方 [!DNL .pem] 法：

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. 證書的CN與當前安裝在服 [!DNL server_cert.pem] 務器上的CN相同。
   1. 憑證的核發目的是伺 *服器**和用戶端*。

      要驗證證書是否具有伺服器和／或客戶機的目的代碼，可使用以下命令：

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      對於伺服器證書，兩個命令都應產生：

      ```
      custom_communications_cert.pem: OK
      ```

      對於客戶端證書，只需要第二個命令才能返回 [!DNL OK]。

1. 將每台伺服器的自定義證書安裝 **到伺服器** 的「證書」目錄中 [!DNL custom_communications_cert.pem]。

1. 使用文字編輯器，將下列行加入「處理伺服器的元件」和「處理伺服器的元件」目錄中的 **Communications** .cfg *檔案，直接在第一行(***[!DNL component = CommServer])下方：

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. 重新啟動所有伺服器。

**關於證書失敗警告**

當Insight伺服器或用戶端在 **Certificates** 目錄中尋找授權憑證時，會嘗試針對Insight CA憑證的硬式編碼復本來驗證所有憑證(除 ****[!DNL trust_ca_cert.pem])，此復本會失敗於目錄中的任何自訂憑證。 伺服器發出以下警告：

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

此警告可安全地忽略。
