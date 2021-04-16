---
description: Adobe為您特定應用程式開發的描述檔和查閱檔案是內部描述檔，可提供度量、維度和工作區，以便分析資料集。
title: 安裝設定檔和查閱檔案
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# 安裝設定檔和查閱檔案{#installing-profiles-and-lookup-files}

Adobe為您特定應用程式開發的描述檔和查閱檔案是內部描述檔，可提供度量、維度和工作區，以便分析資料集。

與Adobe提供的所有其他內部配置檔案一樣，這些配置檔案不應更改。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。

Adobe會將應用程式的描述檔和查閱檔案分發為[!DNL .zip]檔案。 每個zip檔案都會針對應用程式命名，其描述檔和查閱檔案都包含在應用程式中。 （例如，[!DNL Site52.zip]包含網站v5.2的設定檔。） [!DNL .zip]檔案包含兩個資料夾（[!DNL Lookups]和[!DNL Profiles]）。

>[!NOTE]
>
>如果您尚未擁有包含應用程式設定檔和查閱檔案的安裝檔案，請在開始之前從AdobeFTP網站下載。

您必須在處理並執行資料集描述檔的[!DNL Insight Server]機器上安裝描述檔及其查閱檔案。 如果運行[!DNL Insight Server]群集，則必須在主伺服器上安裝這些檔案。 有關資料集配置檔案的資訊，請參見&#x200B;*資料集配置指南*。

**為您的Adobe應用程式安裝配置檔案**

1. 從Adobe提供給您的[!DNL .zip]檔案開啟[!DNL Profiles]資料夾。

1. 將[!DNL .zip]檔案中[!DNL Profiles]資料夾中的所有資料夾複製到[!DNL Insight Server]安裝目錄中的[!DNL Profiles]資料夾。 您希望[!DNL Insight Server]上的&#x200B; [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>*&#x200B;資料夾最後出現，如以下範例所示。 您的實際描述檔名稱可能不同。

   ![](assets/win_installprofiles.png)

1. 導航至&#x200B; [!DNL Profiles\]*&lt;[!DNL dataset profile name]>*&#x200B;資料夾（位於安裝[!DNL Insight Server]的目錄中），並在此目錄中找到[!DNL profile.cfg]檔案。

   >[!NOTE]
   >
   >如果您是第一次安裝描述檔，可以使用提供的範例描述檔做為資料集描述檔。 在[!DNL Insight Server]安裝目錄的[!DNL Profiles\Sample]資料夾中，您可以找到[!DNL profile.cfg]檔案（其名稱可能類似[!DNL profile.cfg.offline]）的「範例」描述檔。

1. 使用文本編輯器（如記事本）開啟[!DNL profile.cfg]檔案並執行以下操作：

   1. 在「目錄」向量中為內部配置檔案添加條目。 配置檔案名稱與複製到[!DNL Insight Server]電腦上[!DNL Profiles]資料夾的目錄的名稱相對應。

   1. 根據需要更新目錄數。
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
      >您為[!DNL profile.cfg]檔案中的「公用名稱」指定的&#x200B;*serverCommonName*，對應您正在處理並執行資料集描述檔的[!DNL Insight Server]機器的伺服器公用名稱。 如需更新[!DNL profile.cfg]以讓資料集描述檔在[!DNL Insight Server]叢集上執行的指示，請參閱[ Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)。

1. 儲存檔案。如果檔案的名稱不同，請務必將它儲存為[!DNL profile.cfg]。

**若要安裝Adobe應用程式的查閱檔案**

1. 從Adobe提供給您的[!DNL .zip]檔案開啟[!DNL Lookups]資料夾。

1. 將[!DNL .zip]檔案中[!DNL Lookups]資料夾中的所有資料夾複製到[!DNL Insight Server]安裝目錄中的[!DNL Lookups]資料夾。 您希望[!DNL Insight Server]上的&#x200B; [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>*&#x200B;資料夾最後出現，如以下範例所示。 您的實際描述檔名稱可能不同。

   ![](assets/win_installLookups.png)
