---
description: 自訂憑證的使用指示。
title: 在 Data Workbench 中使用自訂憑證
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
exl-id: f813d599-723f-4b5d-a0b5-f4d71c1b1a22
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 98%

---

# 在 Data Workbench 中使用自訂憑證{#using-custom-certificates-in-data-workbench}

{{eol}}

自訂憑證的使用指示。

Data Workbench 用戶端或伺服器所使用的憑證，都需由受信任的 CA (憑證授權中心) 簽署。Data Workbench 客戶會收到由 Visual Sciences CA 簽署的憑證。Data Workbench 軟體信任該憑證，因為 [!DNL trust_ca_cert.pem] (隨著 Insight 軟體一起提供，並儲存在伺服器和用戶端的 **Certificates** 目錄中) 包含 Visual Sciences CA 的&#x200B;*根 CA 憑證*。當用戶端或伺服器使用 SSL 彼此通訊時，該憑證會用於軟體授權和驗證。只有 Visual Sciences CA 發行的憑證才能用於授權，而其他憑證則可用於通訊和驗證。Visual Sciences 之外的 CA 所發行的憑證在下文稱為&#x200B;*自訂憑證。*

**重要注意事項：**&#x200B;對於伺服器和用戶端，Data Workbench 軟體使用安裝於用戶端或伺服器的 **Certificates** 目錄中的憑證檔案，或是其設定中明確識別的憑證。不過，[Windows Certificate Store](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) 也可以用於用戶端。

以下指示說明使用自訂憑證在 Data Workbench 用戶端和伺服器之間通訊時應遵循的程序。並非每個細節都是硬性要求，程序中可運用不同的變化。不過，以下程序經測試成功。

## 設定自訂用戶端憑證 {#section-2083fd41973e451fa404e7a4ae4da591}

1. 將發行 CA 的憑證新增至 [!DNL trust_cert_ca.pem]，該憑證安裝於用戶端的 **Certificates** 目錄中，並安裝於每個叢集中要使用此自訂憑證存取之每個伺服器的相同目錄。

1. 為叢集中的每個伺服器取得自訂憑證，其條件如下：

   1. 將憑證格式化為 [!DNL .pem] 憑證。
   1. 憑證包含其金鑰且未加密 (亦即不含密碼/密碼短語)。

      憑證包含其金鑰，且有以下其中一行：

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      從 [!DNL .pem] 憑證移除密碼短語的一種方法：

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. 憑證有 CN、O、OU 等，根據伺服器的 [!DNL Access Control.cfg] 檔案中適用於此用戶端的要求。
   1. 憑證已以 *用途&#42;&#42;&#42;* of *客戶* （或兩者） *伺服器* **和** *客戶*)。

      若要確認憑證有 server 和/或 client 目的碼，可以使用以下命令：

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      對於伺服器憑證，這兩個命令都應該會產生：

      ```
      custom_communications_cert.pem: OK
      ```

      對於用戶端憑證，只需第二個命令就能產生 [!DNL OK]。

1. 將憑證放在用戶端的 **Certificates** 目錄中。
1. 對於您要使用此憑證的每個叢集，在 [!DNL Insight.cfg] 檔案中的 *serverInfo* 底下，確認 *custom client cert* 已命名如下：

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:
   <my_custom_client_cert.pem>
   ```

## 設定自訂伺服器憑證 {#setting-up-custom-server-certificates}

本節假設您的叢集已啟動且執行中、使用 Visual Sciences 發行的憑證，而且設定遵循常規 (例如主要伺服器的 *Components for Processing Servers* 目錄同步到所有 DPU 的 *Components* 目錄)。

1. 將發行 CA 的憑證新增至 [!DNL trust_cert_ca.pem]，該憑證安裝於叢集中的每個伺服器上，並安裝於需要與此叢集通訊的每個用戶端上。
1. 為叢集中的每個伺服器取得自訂憑證，其要求如下：

   1. 將自訂憑證格式化為 [!DNL .pem] 憑證。
   1. 憑證包含其金鑰且未加密 (亦即不含密碼/密碼短語)。

      憑證包含其金鑰，且有以下其中一行：

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      從 [!DNL .pem] 憑證移除密碼短語的一種方法：

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. 憑證的 CN 與目前安裝於伺服器上的 [!DNL server_cert.pem] 相同。
   1. 憑證發行時具有 *server* 和 *client* 目的碼。

      若要確認憑證有 server 和/或 client 目的碼，可以使用以下命令：

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      對於伺服器憑證，這兩個命令都應該會產生：

      ```
      custom_communications_cert.pem: OK
      ```

      對於用戶端憑證，只需第二個命令就能產生 [!DNL OK]。

1. 將每個伺服器的自訂憑證安裝在伺服器的 **Certificates** 目錄中，做為 [!DNL custom_communications_cert.pem]。

1. 使用文字編輯器，將以下一行新增至 *Components* 和 *Components for Processing Servers* 目錄的 **Communications.cfg** 檔案中，直接加在第一行 ([!DNL component = CommServer]) 之下：

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. 重新啟動所有伺服器。

**關於憑證失敗警告**

當 Insight 伺服器或用戶端尋找 **Certificates** 目錄中的 **license** 憑證時，它會嘗試針對 Insight CA 憑證的硬式編碼複本，來驗證所有憑證 ([!DNL trust_ca_cert.pem] 除外)，這使得目錄中的任何自訂憑證都會驗證失敗。伺服器會發出此警告：

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

此警告可以安全地忽略。
