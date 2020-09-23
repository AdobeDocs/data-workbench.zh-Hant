---
description: Adobe為您特定應用程式開發的描述檔和查閱檔案是內部描述檔，可提供度量、維度和工作區，以便分析資料集。
solution: Analytics
title: 安裝設定檔和查閱檔案
uuid: edc670a6-ebc9-4a20-a66f-81dd4adf7433
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---


# 安裝設定檔和查閱檔案{#installing-profiles-and-lookup-files}

Adobe為您特定應用程式開發的描述檔和查閱檔案是內部描述檔，可提供度量、維度和工作區，以便分析資料集。

如同Adobe提供的所有其他內部設定檔，這些設定檔不應變更。 所有自訂都必須發生在您的資料集、角色特定的描述檔或您建立的其他描述檔中。

Adobe會將您應用程式的設定檔和查閱檔案分發為 [!DNL .zip] 檔案。 每個zip檔案都會針對應用程式命名，其描述檔和查閱檔案都包含在應用程式中。 (例如，包 [!DNL Site52.zip] 含網站v5.2的設定檔。) 檔 [!DNL .zip] 案包含兩個資料夾( [!DNL Lookups] 和 [!DNL Profiles])。

>[!NOTE]
>
>如果您尚未擁有包含應用程式設定檔和查閱檔案的安裝檔案，請在開始之前從Adobe FTP網站下載。

您必須在您處理和執行資料集描述檔的 [!DNL Insight Server] 電腦上安裝描述檔及其查閱檔案。 如果您正在運行群 [!DNL Insight Server] 集，則必須在主伺服器上安裝檔案。 如需資料集設定檔的詳細資訊，請參 *閱資料集設定指南*。

**為Adobe應用程式安裝設定檔**

1. 從Adobe提 [!DNL Profiles] 供給您的檔 [!DNL .zip] 案中開啟檔案夾。

1. 將檔案中資料夾內的所 [!DNL Profiles] 有資料夾復 [!DNL .zip] 制到安 [!DNL Profiles] 裝目錄中的 [!DNL Insight Server] 資料夾。 您最後想在您的&#x200B; [!DNL ...\Profiles\]*&lt;[!DNL internal profile name]>資料夾上*[!DNL Insight Server] 找到資料夾，如下列範例所示。 您的實際描述檔名稱可能不同。

   ![](assets/win_installprofiles.png)

1. 導覽至您安裝&#x200B; [!DNL Profiles\]*的目錄中的[!DNL dataset profile name]&lt;* >資料夾，並 [!DNL Insight Server] 在此目錄中 [!DNL profile.cfg] 找到檔案。

   >[!NOTE]
   >
   >如果您是第一次安裝描述檔，可以使用提供的範例描述檔做為資料集描述檔。 您可以在安 [!DNL profile.cfg] 裝目錄的資料夾中，找到Sample描述檔的檔案(可 [!DNL profile.cfg.offline]能會命名為類似 [!DNL Profiles\Sample][!DNL Insight Server] 的)。

1. 使用文 [!DNL profile.cfg] 字編輯器（如記事本）開啟檔案，並執行下列動作：

   1. 在「目錄」向量中為內部配置檔案添加條目。 配置檔案名稱與複製到電腦上資料夾的目 [!DNL Profiles] 錄的名 [!DNL Insight Server] 稱。

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
      >您在檔 *案中為「公用名稱」指定的serverCommonName* ，與您正在處理和執行資料集設定檔的 [!DNL profile.cfg][!DNL Insight Server] 機器的伺服器公用名稱相對應。 如需更新資料集 [!DNL profile.cfg] 設定檔以便在叢集上執行的指示 [!DNL Insight Server] ，請參閱 [Insight Server Clusters](../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-abt-ins-svr-clsters.md)。

1. 儲存檔案。請務必將檔案儲存為 [!DNL profile.cfg] 以不同方式命名。

**若要安裝Adobe應用程式的查閱檔案**

1. 從Adobe提 [!DNL Lookups] 供給您的檔 [!DNL .zip] 案中開啟檔案夾。

1. 將檔案中資料夾內的所 [!DNL Lookups] 有資料夾復 [!DNL .zip] 制到安 [!DNL Lookups] 裝目錄中的 [!DNL Insight Server] 資料夾。 您最後想在您的&#x200B; [!DNL ...\Lookups\]*&lt;[!DNL internal profile name]>資料夾上*[!DNL Insight Server] 找到資料夾，如下列範例所示。 您的實際描述檔名稱可能不同。

   ![](assets/win_installLookups.png)

