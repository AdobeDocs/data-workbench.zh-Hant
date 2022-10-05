---
description: 安裝Insight程式檔案後，您必須下載並安裝由Adobe提供給您的數位憑證。
title: 下載和安裝數位憑證(Insight)
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
exl-id: 0dff95ae-880b-45d5-96df-4eb6bea58891
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2744'
ht-degree: 73%

---

# 下載和安裝數位憑證{#downloading-and-installing-the-digital-certificate}

{{eol}}

安裝Insight程式檔案後，您必須下載並安裝由Adobe提供給您的數位憑證。

## 下載和安裝數位憑證 {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

安裝Insight程式檔案後，您必須下載並安裝由Adobe提供給您的數位憑證。

## 了解數位憑證 {#concept-9eed01c8d95440cda6ce29d68e65098c}

Adobe 使用 X.509 數位憑證來識別和驗證實作的用戶端和伺服器元件。

<!--
c_undst_dgtl_crtf.xml
-->

安裝Insight時，您必須安裝數位憑證，授權指名的個人（例如Jane Smith）使用已安裝的用戶端應用程式。

>[!NOTE]
>
>如果您需要將Insight移轉至其他電腦或其他指名使用者，必須向Adobe取得新憑證。 若要取得新憑證，請連絡 Adobe 客戶服務。

Insight提供此數位憑證，以存取伺服器元件。 伺服器元件的管理員可以根據使用者憑證中顯示的通用名稱或組織單位值，限制對伺服器資源的存取。

與 Adobe 應用程式一併安裝的 X.509 數位憑證也可讓其用戶端和伺服器元件透過安全通訊端層 (SSL) 交換資訊。SSL 使用公開和私密金鑰加密系統，透過 HTTP 保護傳輸安全。Adobe 的 SSL 實作支援 1024 位元 RSA 金鑰，並使用 128 位元 RC4 加密演算法。

除了安全性，您安裝的數位憑證也可作為授權金鑰，讓您執行Insight。 若要正常運作，數位憑證必須是節點鎖定且最新的，否則應用程式將不會啟動。

## 節點鎖定憑證 {#section-984aa8f2f5a1448cadc4afea978aedc9}

節點鎖定憑證是已註冊至安裝該憑證之電腦的數位憑證。 節點鎖定會將憑證與特定節點識別碼（可唯一識別特定電腦的值）建立永久關聯。 要節點鎖定證書，您的電腦必須具有對Adobe許可證伺服器或具有許可證伺服器訪問權限的代理伺服器的Internet訪問權限。

如果您要在無法存取網際網路的電腦上進行安裝，必須如 [在無法存取網際網路的電腦上使用數位憑證](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1).

如果您要在可存取網際網路的電腦上進行安裝，您的數位憑證會在您第一次啟動Insight時自動與節點鎖定。 節點鎖定後，該憑證就無法用於任何其他電腦。 如果您需要將Insight移轉至其他電腦，必須從Adobe取得新的解除鎖定憑證。

## 最新憑證 {#section-0816b031df3e415ab3f0205b720c723e}

除了節點鎖定外，您的數位憑證必須為最新。 若要保持最新狀態，您的憑證必須定期重新驗證 (通常每 30 天一次，但可視您與 Adobe 的合約而定)。如果您的電腦可以訪問網際網路，則重新驗證過程完全透明。 Insight會自動連線至授權伺服器，並在必要時重新驗證憑證。 如果您的電腦無法訪問Internet，則必須按以下部分所述手動安裝更新的證書。

## 在無法存取網際網路的電腦上使用數位憑證 {#section-d3c060131d7f45cda27f68848b704fa1}

如果您要在無法存取網際網路的電腦上進行安裝，必須索取預先鎖定憑證，才能安裝Insight。 預先鎖定憑證是數位憑證，可Adobe手動鎖定至電腦的節點識別碼。

若要要求預先鎖定憑證，您必須傳送節點識別碼和憑證號碼給Adobe客戶服務。 若要取得您電腦的節點識別碼，請連絡Adobe客戶服務以要求Adobe [!DNL Node Identifier] 工具。 您也可以從Insight在嘗試連線至License Server且無法連線時發出的警報中取得節點識別碼。 收到預先鎖定憑證時，請依照 [安裝數位憑證](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38).

需要重新驗證憑證時，您必須從授權伺服器下載經過驗證的新憑證，然後在電腦上重新安裝(除非您同意Adobe狀態)。

## 安裝數位憑證 {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**若要下載及安裝數位憑證**

1. 開啟網頁瀏覽器以 [!DNL https:\\license.visualsciences.com].

   >[!NOTE]
   >
   >您的瀏覽器可能會在這時提示您提供數位憑證。如果有，請按一下 **[!UICONTROL Cancel]** 關閉對話框。

1. 在登入畫面中，輸入 Adobe 提供的「[!DNL Account Name]」和「[!DNL Password]」，然後按一下「**[!UICONTROL login]**」。
1. 找出已針對您的Insight例項核發的憑證( *您的名稱*.pem)，然後按一下 ![](assets/btn_save_certificatedownload.PNG) 與該憑證相關聯的圖示。
1. 提示儲存憑證時，請按一下「**[!UICONTROL Save]**」。
1. 將檔案下載至 [!DNL Certificates] 資料夾（位於您安裝Insight的目錄中）。

   此資料夾包含一個名為 [!DNL trust_ca_cert.pem]. Insight必須一律存在兩個憑證檔案，才能運作。

## Windows 憑證存放區 {#concept-4acb13b7de9340ea8cde8ad84b93358d}

Windows 憑證存放區可讓您將用戶端的憑證和私密金鑰存放在 Windows 憑證存放區中，以便與伺服器進行 SSL 通訊。

<!--
crypto-api.xml
-->

適用於用戶端的 Windows 憑證存放區是一項新功能，可讓您將 SSL 通訊憑證和私密金鑰存放在 Windows 憑證存放區，而非 `Insight/Certificates/<CertName>.pem` 檔案中。如果您將憑證存放區用於其他應用程式，並且要集中管理憑證，或是因使用者享有額外的 Windows 稽核記錄功能 (由 Windows 憑證存放區提供) 而使用憑證存放區，建議您使用 Windows 憑證存放區。

>[!NOTE]
>
>目前仍可使用現有的 `<Common Name>.pem` 檔案，維持透過授權伺服器進行授權的方式，且從憑證存放區取得的憑證只會用於與您指定的伺服器通訊。

## 先決條件 {#section-69b18600052145ff8e5299b7123e69c5}

1. 您必須能存取 [!DNL certmgr.msc] 檔案，並能夠將憑證和金鑰匯入 **Personal** 存放區。(根據預設，大部分 Windows 使用者都符合條件。)

1. 進行設定的使用者必須有 **OpenSSL** 命令列工具的副本。
1. 伺服器和用戶端必須已設定為使用自訂SSL憑證，提供將用戶端憑證儲存在Windows憑證存放區，而非儲存在 **憑證** 目錄。

## 設定 Windows 憑證存放區 {#section-3629802122e947d4b4f63e8b732cfe27}

按照下列步驟啟用適用於用戶端的 Windows 憑證存放區：

**步驟 1：將使用者的 SSL 憑證和私密金鑰匯入 Windows 憑證存放區。**

在 [在Data Workbench中使用自訂憑證](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) 系統會將您導向至將SSL憑證和金鑰放入下列目錄：

```
<
<filepath>
  DWB Install folder
</filepath>>\Certificates\
```

憑證的名稱為 `<Common Name>.pem` 例如Analytics Server 1.pem（不是trust_ca_cert.pem檔案）。

必須將憑證和私密金鑰先從[!DNL pem] 格式轉換為 [!DNL .pfx] 格式 (例如 [!DNL pkcs12.pfx]) 才能匯入。

1. 開啟命令提示字元或終端機，然後導覽至目錄：

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. 使用下列引數執行 [!DNL openssl] (含實際的 [!DNL .pem] 檔案名稱)：

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   如果系統提示，請按 **Enter** 以略過輸入匯出密碼。

1. 在執行提示、開始功能表或命令列執行 [!DNL certmgr.msc]。
1. 開啟目前使用者的 **Personal** 憑證存放區。

   ![](assets/6_5_crypto_api_0.png)

1. 以右鍵按一下 **Certificates**，然後按一下&#x200B;**「所有工作** > **匯入」**。

   確認選取&#x200B;**「目前使用者」**&#x200B;選項，然後按&#x200B;**「下一步」**。

   ![](assets/6_5_crypto_api_4.png)

1. 按一下&#x200B;**「瀏覽」**，然後選取先前建立的 `<CommonName>.pfx` 檔案。您必須將副檔名下拉方塊從「X.509 憑證」變更為 **「個人資訊交換」**&#x200B;或&#x200B;**「所有檔案」**，才能看到該檔案。

   選取該檔案，按一下&#x200B;**「開啟」**，然後按&#x200B;**「下一步」**。

1. 請勿輸入密碼，並確認只選取&#x200B;**「將這個金鑰設成可匯出」**&#x200B;和&#x200B;**「包含所有延伸內容」**&#x200B;選項。

   ![](assets/6_5_crypto_api_3.png)

   按&#x200B;**「下一步」**。

1. 確認已選取&#x200B;**「將所有憑證放入以下的存放區」**，且所列的憑證存放區為 **Personal**。(如果您為進階使用者，此時可選取其他存放區，但稍後必須變更設定。)

1. 按&#x200B;**「下一步」**，然後按一下&#x200B;**「完成」**。您應該會看到一個對話方塊，告訴您匯入成功，並在存放區的 Certificates 檔案夾中看到您的憑證。

   >[!NOTE]
   >
   >請特別注意&#x200B;**「核發對象」**&#x200B;和&#x200B;**「核發人員」**&#x200B;欄位。下一步需要這些資訊。

**步驟 2：編輯 Insight.cfg 檔案。**

必須編輯 [!DNL Insight.cfg] 檔案，才能指示 Data Workbench 使用 Windows 憑證存放區功能。此檔案的每個伺服器項目都必須指定一些其他參數。如果省略這些參數，工作站會預設為使用現有憑證設定。如果已指定參數但值不正確，工作站會進入錯誤狀態，而您必須參考記錄檔以取得錯誤資訊。

1. 開啟 **Insight.cfg** 檔案 (位於 **Insight** 安裝目錄)。

1. 向下捲動至要設定的伺服器項目。如果您想要將 Windows 憑證存放區用於每個伺服器，必須對 [!DNL serverInfo] 物件向量中的每個項目進行下列修改。
1. 將下列參數新增至其 [!DNL Insight.cfg] 檔案。您可以在工作站執行此操作，或手動將下列參數新增至 [!DNL serverInfo] 物件。(請務必使用空格而非定位字元，並確認此檔案中沒有其他拼字或語法錯誤。)

   ```
   SSL Use CryptoAPI = bool: true
   SSL CryptoAPI Cert Name = string: <Common Name>
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC
   SSL CryptoAPI Cert Store Name = string: My
   ```

   布林值會啟用或停用此功能。憑證名稱與憑證管理員中的&#x200B;**「核發對象」**&#x200B;相符。憑證核發者名稱與&#x200B;**「核發人員」**&#x200B;相符，且&#x200B;**「存放區名稱」**&#x200B;必須與憑證存放區名稱相符。

   >[!NOTE]
   >
   >憑證管理員 (certmgr.msc) 中的名稱「個人」實際上是指憑證存放區&#x200B;**「My」。**&#x200B;因此，如果您依建議將 SSL 通訊憑證和金鑰 (.PFX) 匯入 **Personal** 憑證存放區，必須將&#x200B;**「SSL CryptoAPI Cert Store Name」**&#x200B;字串設為「My」。將此參數設為「Personal」會無法執行，這是 Windows 憑證存放區的特性。

   您可在此取得預先定義的系統存放區完整清單：[https://msdn.microsoft.com/zh-tw/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/zh-tw/library/windows/desktop/aa388136%28v=vs.85%29.aspx)。您的系統可能有其他憑證存放區。如果您想使用「個人」(例如&#x200B;**「My」**) 以外的存放區，必須取得憑證存放區的正式名稱，並在 [!DNL Insight.cfg] 檔案中提供該名稱。(Windows 文件將系統存放區名稱「My」不一致地稱為「My」和「MY」。此參數似乎不區分大小寫。)

1. 新增這些參數，並確認值與 Windows 憑證管理員中的清單相符後，請儲存 [!DNL Insight.cfg] 檔案。

您現在可以啟動工作站 (或中斷伺服器連線/重新連線至伺服器)。Data Workbench 應會從憑證存放區載入憑證和金鑰，並正常連線。

## 記錄輸出 {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

找不到憑證或憑證無效時，系統會將此錯誤訊息擲回 [!DNL HTTP.log] 檔案。

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>可設定 [!DNL L4.cfg] 檔案來啟用 L4 記錄架構 (請洽詢您的帳戶管理員以進行設定)。

## 在 Data Workbench 中使用自訂憑證 {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

自訂憑證的使用指示。

<!--
using-custom-certificates-DWB.xml
-->

Data Workbench 用戶端或伺服器所使用的憑證，都需由受信任的 CA (憑證授權中心) 簽署。Data Workbench 客戶會收到由 Visual Sciences CA 簽署的憑證。Data Workbench 軟體信任該憑證，因為 [!DNL trust_ca_cert.pem] (隨著 Insight 軟體一起提供，並儲存在伺服器和用戶端的 **Certificates** 目錄中) 包含 Visual Sciences CA 的&#x200B;*根 CA 憑證*。當用戶端或伺服器使用 SSL 彼此通訊時，該憑證會用於軟體授權和驗證。只有 Visual Sciences CA 發行的憑證才能用於授權，而其他憑證則可用於通訊和驗證。Visual Sciences 之外的 CA 所發行的憑證在下文稱為&#x200B;*自訂憑證。*

**重要注意事項：**&#x200B;對於伺服器和用戶端，Data Workbench 軟體使用安裝於用戶端或伺服器的 **Certificates** 目錄中的憑證檔案，或是其設定中明確識別的憑證。不過，Windows Certificate Store 也可以用於用戶端。

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

1. 使用文字編輯器，將以下一行新增至 **Components** 和 *Components for Processing Servers* 目錄的 *Communications.cfg* 檔案中，直接加在第一行 ([!DNL component = CommServer]) 之下：

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

## 字串加密 {#concept-35da0b53650a4d7e82b240ad27f6d45a}

在用戶端和伺服器之間通訊時加密密碼和其他字串。

<!--
string_encryption.xml
-->

在 Data Workbench 用戶端 (工作站) 和伺服器之間通訊時，您可以儲存具有 *EncryptedString* 類型的 Value 參數 (例如密碼)。這會隱藏參數，並將字串與傳回的對應金鑰儲存至伺服器的 *Windows Credential Store*。這主要儲存匯出時使用的認證，但是可用於加密任何參數。

* 在 Server\**EncryptStrings** 新增了新檔案夾。

   這是您將設定檔設定為加密字串的位置。

* 在 Server\Component\**EncryptedStrings.cfg** 新增了新設定檔。

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   此檔案輪詢 *Server*\*EncryptStrings* 檔案夾以尋找加密設定檔。

**若要加密字串**：

1. 為字串建立 **EncryptedStrings.cfg** 設定檔，其欄位設定如下：

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier
     Value = string: // Value to be encrypted
   ```

   * *Value* - 此欄位包含須加密的純文字字串。

      這僅是伺服器端加密。*Value* 設定僅在伺服器電腦上加密。

   * *Name* - 此欄位包含識別加密字串的值。
   * *EncryptValue* - 此欄位在輸入設定檔中將保留空白。加密值將傳回至此欄位。

   您可以為不同欄位新增多個 **NameEncryptValuePair** 值，以進行加密。

   >[!NOTE]
   >
   >所有空白的 Value 欄位都將移除。

1. 將 **EncryptedStrings.cfg** 檔案儲存至 Server\**EncryptStrings** 檔案夾。

**輸出檔案**

將產生一個與輸入檔案同名的輸出檔案，其名稱為 &lt;*filename*>.*encrypted* (副檔名)。例如，如果輸入檔案名為 *sample.cfg*，則輸出檔案名為 *sample.cfg.encrypted*。
