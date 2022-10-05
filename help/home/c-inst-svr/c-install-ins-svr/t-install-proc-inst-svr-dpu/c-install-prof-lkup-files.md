---
description: Adobe為特定應用程式開發的設定檔和查閱檔案是內部設定檔，可提供量度、維度和工作區，以便對資料集進行分析。
title: 安裝設定檔和查閱檔案
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 2%

---

# 安裝設定檔和查閱檔案{#installing-profiles-and-lookup-files}

{{eol}}

Adobe為特定應用程式開發的設定檔和查閱檔案是內部設定檔，可提供量度、維度和工作區，以便對資料集進行分析。

與Adobe提供的所有其他內部設定檔一樣，這些設定檔不應變更。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。

Adobe將應用程式的設定檔和查閱檔案分發為 [!DNL .zip] 檔案。 每個zip檔案的名稱都是針對其設定檔和查閱檔案所在的應用程式。 (例如， [!DNL Site52.zip] 包含網站v5.2的設定檔檔案。) 此 [!DNL .zip] 檔案包含兩個資料夾( [!DNL Lookups] 和 [!DNL Profiles])。

>[!NOTE]
>
>如果您尚未擁有包含應用程式設定檔和查閱檔案的安裝檔案，請先從AdobeFTP站台下載，再開始。

您必須在 [!DNL Insight Server] 處理和執行資料集設定檔的電腦。 如果您執行的是 [!DNL Insight Server] 群集中，必須在主伺服器上安裝檔案。 如需資料集設定檔的相關資訊，請參閱 *資料集組態指南*.

**為Adobe應用程式安裝配置檔案**

1. 開啟 [!DNL Profiles] 資料夾 [!DNL .zip] 檔案(由Adobe提供)。

1. 複製 [!DNL Profiles] 檔案夾 [!DNL .zip] 檔案 [!DNL Profiles] 檔案夾 [!DNL Insight Server] 安裝目錄。 您最後想要得到[!DNL ...\配置檔案\]*&lt; [!DNL internal profile name]>* 資料夾 [!DNL Insight Server] 如下列範例所示。 您的實際設定檔名稱可能會有所不同。

   ![](assets/win_installprofiles.png)

1. 導覽至&#x200B; [!DNL Profiles\]*&lt; [!DNL dataset profile name]>* 資料夾（位於安裝的目錄中） [!DNL Insight Server] 並找到 [!DNL profile.cfg] 檔案。

   >[!NOTE]
   >
   >如果您是第一次安裝設定檔，可以使用提供的範例設定檔作為資料集設定檔。 您可以找到 [!DNL profile.cfg] 檔案(可能會命名為 [!DNL profile.cfg.offline])，以取得 [!DNL Profiles\Sample] 檔案夾 [!DNL Insight Server] 安裝目錄。

1. 開啟 [!DNL profile.cfg] 檔案（使用文本編輯器，如Notepad），並執行以下操作：

   1. 在目錄向量中為內部配置檔案添加條目。 配置檔案名稱對應於您複製到的目錄的名稱 [!DNL Profiles] 資料夾 [!DNL Insight Server] 機器。

   1. 視需要更新目錄數。
   1. 將伺服器的公用名稱添加到此檔案的公用名稱行中，如下所示：

      ```
      Profile = profileInfo: 
      Directories = vector: n+1 items
        0 = string: Base\\
        1 = string: internal profile name 1\\
        2 = string: internal profile name 2\\
      . . .
        n = string: internal profile name n\\
      Processing Servers = vector: 1 items
        0 = ProfileServerInfo: 
          Common Name = string: serverCommonName
          Server = string: 
      ```

      >[!NOTE]
      >
      >此 *serverCommonName* 在 [!DNL profile.cfg] 檔案與 [!DNL Insight Server] 處理和執行資料集設定檔的電腦。 更新說明 [!DNL profile.cfg] 讓資料集設定檔在 [!DNL Insight Server] 群集，請參見 [Insight Server叢集](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md).

1. 儲存檔案。請務必將檔案儲存為 [!DNL profile.cfg] 如果名字不同。

**為Adobe應用程式安裝查閱檔案**

1. 開啟 [!DNL Lookups] 資料夾 [!DNL .zip] 檔案(由Adobe提供)。

1. 複製 [!DNL Lookups] 檔案夾 [!DNL .zip] 檔案 [!DNL Lookups] 檔案夾 [!DNL Insight Server] 安裝目錄。 您最後想要得到[!DNL ...\查詢\]*&lt; [!DNL internal profile name]>* 資料夾 [!DNL Insight Server] 如下列範例所示。 您的實際設定檔名稱可能會有所不同。

   ![](assets/win_installLookups.png)
