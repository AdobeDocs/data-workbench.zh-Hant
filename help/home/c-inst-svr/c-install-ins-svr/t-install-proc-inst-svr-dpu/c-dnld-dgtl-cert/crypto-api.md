---
description: Windows憑證存放區可讓您將用戶端的憑證和私密金鑰儲存在Windows憑證存放區中，以便與伺服器進行SSL通訊。
title: Windows 憑證存放區
uuid: a8021295-375a-460b-8686-acf3bc43cd17
translation-type: tm+mt
source-git-commit: a766b64ef809e2223fed869d8d63b75f270a3d39
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 0%

---


# Windows 憑證存放區{#windows-certificate-store}

Windows憑證存放區可讓您將用戶端的憑證和私密金鑰儲存在Windows憑證存放區中，以便與伺服器進行SSL通訊。

用戶端的Windows憑證存放區是一項新功能，可讓您將SSL通訊憑證和私密金鑰儲存在Windows憑證存放區中，而非儲存在檔 `Insight/Certificates/<CertName>.pem` 案中。 如果您將憑證存放區用於其他應用程式，並希望在單一位置進行憑證管理，或是想要使用Windows憑證存放區提供之額外Windows稽核記錄的使用者，則最好使用Windows憑證存放區。

>[!NOTE]
>
>授權伺服器的授權仍會使用現有檔案來 `<Common Name>.pem` 維護，而且從憑證存放區取得的憑證將僅用於與您指定的伺服器通訊。

## 必備條件 {#section-69b18600052145ff8e5299b7123e69c5}

1. 您必須擁有檔案的存 [!DNL certmgr.msc] 取權，並能夠將憑證和金鑰匯入個人 **商店** 。 （對於大部分的Windows使用者，這個預設值應為true。）

1. 執行配置的用戶必須有 **OpenSSL** 命令行工具的副本。
1. 伺服器和客戶端必須已配置為使用自定義SSL證書(如 [Using Custom Certificates](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd))中所述)，以指示將客戶端證書儲存在Windows證書儲存中，而不是儲存在 **** Certificates目錄中。

## 配置Windows證書儲存 {#section-3629802122e947d4b4f63e8b732cfe27}

按照以下步驟啟用Windows客戶端證書儲存：

**步驟1:將使用者的SSL憑證和私密金鑰匯入Windows憑證商店。**

使 [用自訂憑證](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/using-custom-certificates-dwb.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) 時，您會將SSL憑證和金鑰放在下列目錄中：

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

憑證的名稱為 `<Common Name>.pem` (例如 [!DNL Analytics Server 1.pem] (非 [!DNL trust_ca_cert.pem] 檔案)。

必須先從轉換憑證和私密金鑰，才能匯入。 [!DNL pem] 格式 [!DNL .pfx] 化，例如 [!DNL pkcs12.pfx] )。

1. 開啟命令提示符或終端，然後導航到目錄：

   ```
   <CommonName>.pem c: cd \<DWB Install folder \Certificates
   ```

1. 使用 [!DNL openssl] 下列引數(使用實際的檔 [!DNL .pem] 案名稱)執行：

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   如果出現提示，請按 **下Enter** 以略過輸入匯出密碼。

1. 從運 [!DNL certmgr.msc] 行提示符、開始菜單或命令行運行。
1. 開啟目 **前使用者** 的個人憑證存放區。

   ![](assets/6_5_crypto_api_0.png)

1. 按一下右鍵「證 **書** 」 ，然後單 **擊「所有任務** 」 **> 「**&#x200B;導入」。

   請確定已選 **取「目前使用者** 」選項，然後按一下「下 **一步」**。

   ![](assets/6_5_crypto_api_4.png)

1. 按一 **下「瀏覽** 」，然後選 `<CommonName>.pfx` 取先前建立的檔案。 您必須將副檔名下拉式方塊從X.509憑證變更為 **Personal Information Exchange****或All Files** ，才能檢視它。

   選取檔案，然後按一下「 **開啟**」，然後按「下 **一步」**。

1. 請勿輸入密碼，並確保只選擇「將此鍵標籤為可導出 **」** 和「包含所有擴展屬性 **** 」選項。

   ![](assets/6_5_crypto_api_3.png)

   按&#x200B;**「下一步」**。

1. 請確定已選 **取「將所有憑證放入下列商店** 」，且所列的憑證商店為「 **個人」**。 （如果您是進階使用者，此時可以選取其他商店，但您稍後必須變更設定。）

1. 按一下「 **Next** (下一步 **)」 ，然後按一下「** Finish（完成）」。 您應該會看到一個對話方塊，告訴您匯入成功，並在商店的「憑證」資料夾中看到您的憑證。

   >[!NOTE]
   >
   >請特別留意「發 **布方** 」 **及「發佈方** 」欄位。 下一步就需要這些。

**步驟2:編輯Insight.cfg檔案。**

必 [!DNL Insight.cfg] 須編輯檔案，才能引導資料工作台使用Windows憑證商店功能。 此檔案中的每個伺服器條目必須指定一些其他參數。 如果省略這些參數，則工作站將預設使用現有證書配置。 如果指定了參數，但值不正確，則工作站將進入錯誤狀態，您必須參考日誌檔案以獲取錯誤資訊。

1. 開啟 **Insight.cfg檔** (位於 **** Insight安裝目錄)。

1. 向下滾動到要配置的伺服器條目。 如果您想要針對每個伺服器使用Windows憑證存放區，則必須對物件向量中的每個項目進行這些修 [!DNL serverInfo] 改。
1. 將這些參數新增至其 [!DNL Insight.cfg] 檔案。 您可以從工作站執行此操作，也可以通過向對象中添加以下參數來手動 [!DNL serverInfo] 執行。 (請務必使用空格來取代Tab字元，而且請勿在此檔案中出現其他印刷樣式或語法錯誤。)

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   布林值會啟用或停用功能。 憑證名稱與憑證管 **理員中的** 「發行者至」相符。 憑證發行者名稱與「 **核發者**」相符，且 **「商店名稱** 」必須與憑證商店名稱相符。

   >[!NOTE]
   >
   >「認證管理員」(certmgr.msc)中的「個人」名稱實際上是指名為 **My的認證商店。** 因此，如果您按建議將SSL通訊憑證和金鑰(.PFX)匯入 **Personal** certificate Store，則必須將 **SSL CryptoAPI Cert Store Name** String設為&quot;My&quot;。 將此參數設為「個人」將無法運作。 這是Windows憑證存放區的特性。

   您可在此處獲得預定義系統儲存的完整清單： [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). 您的系統可能有其他憑證存放區。 如果您想使用「個人」以外的商店(例如 **My**)，則必須取得憑證商店的標準名稱，並在檔案中提供 [!DNL Insight.cfg] 該名稱。 (Windows文檔不一致地將系統儲存名稱「My」稱為「My」和「MY」。 參數似乎不區分大小寫。)

1. 添加這些參數並驗證這些值是否與Windows證書管理器中的清單匹配後，請保存文 [!DNL Insight.cfg] 件。

您現在可以啟動工作站（或斷開／重新連接至伺服器）。 資料工作台應從憑證存放區載入憑證和金鑰，並正常連線。

## 日誌輸出 {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

當找不到憑證或憑證無效時，此錯誤訊息會擲回 [!DNL HTTP.log] 檔案。

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>L4記錄架構可透過設定檔案來啟用(請 [!DNL L4.cfg] 洽詢您的帳戶管理員以設定)。
