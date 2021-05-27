---
description: Adobe為特定應用程式開發的設定檔和查閱檔案是內部設定檔，可提供量度、維度和工作區，以便對資料集進行分析。
title: 安裝設定檔和查閱檔案
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
exl-id: bf9a3bca-e849-47b6-b038-0349f8ec334a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# 安裝設定檔和查閱檔案{#installing-profiles-and-lookup-files}

Adobe為特定應用程式開發的設定檔和查閱檔案是內部設定檔，可提供量度、維度和工作區，以便對資料集進行分析。

與Adobe提供的所有其他內部設定檔一樣，這些設定檔不應變更。 所有自訂都必須發生在您的資料集、角色專屬設定檔或您建立的其他設定檔中。

Adobe將應用程式的設定檔和查閱檔案分發為[!DNL .zip]檔案。 每個zip檔案的名稱都是針對其設定檔和查閱檔案所在的應用程式。 （例如，[!DNL Site52.zip]包含網站v5.2的設定檔檔案。） [!DNL .zip]檔案包含兩個資料夾（[!DNL Lookups]和[!DNL Profiles]）。

>[!NOTE]
>
>如果您尚未擁有包含應用程式設定檔和查閱檔案的安裝檔案，請先從AdobeFTP站台下載，再開始。

您必須在處理及執行資料集設定檔的[!DNL Insight Server]電腦上安裝設定檔及其查閱檔案。 如果運行的是[!DNL Insight Server]群集，則必須在主伺服器上安裝這些檔案。 如需資料集設定檔的相關資訊，請參閱&#x200B;*資料集設定指南*。

**為Adobe應用程式安裝配置檔案**

1. 從[!DNL .zip]檔案開啟[!DNL Profiles]資料夾(由Adobe提供)。

1. 將[!DNL .zip]檔案中[!DNL Profiles]資料夾內的所有資料夾複製到[!DNL Insight Server]安裝目錄中的[!DNL Profiles]資料夾。 您想要在[!DNL Insight Server]上最終顯示&#x200B; [!DNL ...\Profiles\]*&lt; [!DNL internal profile name]>*&#x200B;資料夾，如下列範例所示。 您的實際設定檔名稱可能會有所不同。

   ![](assets/win_installprofiles.png)

1. 導覽至&#x200B; [!DNL Profiles\]*&lt;[!DNL dataset profile name]>*&#x200B;資料夾，位於安裝[!DNL Insight Server]的目錄中，並在此目錄中找到[!DNL profile.cfg]檔案。

   >[!NOTE]
   >
   >如果您是第一次安裝設定檔，可以使用提供的範例設定檔作為資料集設定檔。 在[!DNL Insight Server]安裝目錄的[!DNL Profiles\Sample]資料夾內，可以找到[!DNL profile.cfg]檔案（可能命名為[!DNL profile.cfg.offline]）的Sample配置檔案。

1. 使用文本編輯器（如記事本）開啟[!DNL profile.cfg]檔案，並執行以下操作：

   1. 在目錄向量中為內部配置檔案添加條目。 配置檔案名稱與您複製到[!DNL Insight Server]電腦上[!DNL Profiles]資料夾的目錄名稱相對應。

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
      >您為[!DNL profile.cfg]檔案中的「公用名稱」指定的&#x200B;*serverCommonName*&#x200B;對應於您正在處理和運行資料集配置檔案的[!DNL Insight Server]電腦的伺服器公用名稱。 如需更新[!DNL profile.cfg]以讓資料集設定檔在[!DNL Insight Server]叢集上執行的指示，請參閱[Insight Server叢集](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)。

1. 儲存檔案。如果檔案的名稱不同，請務必將其儲存為[!DNL profile.cfg]。

**為Adobe應用程式安裝查閱檔案**

1. 從[!DNL .zip]檔案開啟[!DNL Lookups]資料夾(由Adobe提供)。

1. 將[!DNL .zip]檔案中[!DNL Lookups]資料夾內的所有資料夾複製到[!DNL Insight Server]安裝目錄中的[!DNL Lookups]資料夾。 您想要在[!DNL Insight Server]上最終顯示&#x200B; [!DNL ...\Lookups\]*&lt; [!DNL internal profile name]>*&#x200B;資料夾，如下列範例所示。 您的實際設定檔名稱可能會有所不同。

   ![](assets/win_installLookups.png)
