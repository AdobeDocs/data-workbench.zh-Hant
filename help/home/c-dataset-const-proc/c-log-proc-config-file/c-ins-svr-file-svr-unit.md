---
description: 有關Insight Server檔案伺服器單元和檔案伺服器設定程式的資訊。
title: 設定 Data Workbench 伺服器檔案伺服器單元
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 2%

---

# 設定 Data Workbench 伺服器檔案伺服器單元{#configuring-a-data-workbench-server-file-server-unit}

有關Insight Server檔案伺服器單元和檔案伺服器設定程式的資訊。

<!--
c_abt_file_svr_units.xml
-->

您可以完成[!DNL Log Processing.cfg]檔案&#x200B;**[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]**&#x200B;節點中的參數，將Data Workbench伺服器(InsightServer64.exe)設定為以檔案伺服器單元(FSU)的形式執行。 當Data Workbench伺服器設定為以FSU執行時，會儲存可由多個處理伺服器(DPU)快速存取的來源檔案（[!DNL .vsl]檔案、文字檔案或XML檔案）。 當Data Workbench伺服器叢集中的DPU存取FSU以讀取記錄檔時，會將記錄檔分割，並保證不會多次處理相同的檔案。

>[!NOTE]
>
>設定提供Data Workbench伺服器叢集（由5到10個DPU組成）的FSU時，應將叢集的主伺服器設為FSU。

有關安裝Data Workbench伺服器群集的資訊，請參閱&#x200B;*伺服器產品安裝與管理指南*。

<!--
c_file_svr_config_proc.xml
-->

如果位置是遠端位置，則處理資料的Data Workbench伺服器電腦會連線至指定的遠端電腦以讀取記錄檔。

在指定為FSU的Data Workbench伺服器電腦上，[!DNL Access Control.cfg]檔案可讓DPU連線至FSU，而[!DNL Communications.cfg]檔案會映射遠端資料檔案的位置。 配置FSU的流程步驟如下：

1. 在主資料工作台伺服器上的[!DNL Log Processing.cfg]檔案中，指定資料來源的類型和來源的位置。 請參閱[指定資料源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383)。

1. 在FSU的[!DNL Access Control.cfg]檔案中，編輯權限以允許DPU連線至FSU以讀取記錄資料。 請參閱[編輯檔案伺服器單元的權限](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef)。

1. 在FSU的[!DNL Communications.cfg]檔案中，編輯[!DNL LoggingServer]和[!DNL FileServer]項的設定，以指定日誌檔案的位置。 請參閱[指定日誌檔案的位置](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0)。

1. 如果您要將資料集設定檔設定為在Data Workbench伺服器叢集上執行，您也必須將叢集的FSU設為建構所有設定檔維度的伺服器：
（僅適用於Data Workbench伺服器叢集）在FSU的[!DNL Communications.cfg]和[!DNL cluster.cfg]檔案中，新增「標準化伺服器」的項目，使FSU成為已建構所有維度的叢集中的伺服器。 請參閱[為群集](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28)建立集中化標準化伺服器。

如需設定要由Data Workbench伺服器叢集處理的資料集設定檔的指示，請參閱&#x200B;*伺服器產品安裝與管理指南*。

>[!NOTE]
>
>以下說明假設所有日誌檔案都位於預設目錄中。 如果您想要將記錄檔儲存在其他目錄中或建立多個記錄路徑，請聯絡Adobe諮詢服務以討論您的特定設定。

## 指定資料源{#section-d2b545db7ab142ffb4be32e040395383}

指定資料集的遠端資料來源時，您必須指定資料來源類型和主資料工作台伺服器上記錄檔的位置。

**指定資料源及其位置**

1. 開啟 [!DNL Log Processing.cfg] 檔案. 請參閱[編輯記錄處理組態檔](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5)。

1. 添加[!DNL Sensor]、日誌檔案或XML資料源。 請參閱[日誌檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)。

1. 完成Log Paths參數。 請參閱[感測器檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009)、[日誌檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)或[XML日誌源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887)。 請務必指定有效的URI。

1. 完成下表中定義的日誌伺服器參數：

<table id="table_5881B8DEFF984BC7A620CEEA3A637912"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 參數 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 名稱 </td> 
   <td colname="col2"> 標識遠程檔案伺服器的名稱。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL伺服器公用名稱 </td> 
   <td colname="col2"> <p> <span class="wintitle"> 檔案</span> 伺服器的SSL憑證上列出的伺服器常見名稱。 </p> <p> 如果「<span class="wintitle">使用SSL</span>」設為false，此參數為選用。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <p>檔案伺服器電腦的地址。 如果<span class="wintitle">名稱</span>符合<span class="wintitle"> SSL伺服器常見名稱</span>，則可保留空白。 </p> <p> 例如：<span class="filepath"> visual.mycompany.com</span>或192.168.1.90。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 連接埠 </td> 
   <td colname="col2"> Data Workbench伺服器電腦與檔案伺服器通訊的埠。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL用戶端憑證 </td> 
   <td colname="col2"> Data Workbench伺服器的<span class="wintitle"> SSL憑證</span>檔案名稱(<span class="filepath"> server_cert.pem</span>)。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用SSL </td> 
   <td colname="col2"> True 或 False. True表示檔案伺服器使用<span class="wintitle"> SSL</span>。 </td> 
  </tr> 
 </tbody> 
</table>

如果DPU需要代理伺服器才能連線至FSU，您必須完成下列參數：

| 參數 | 說明 |
|---|---|
| 代理地址 | Data Workbench伺服器必須用來存取檔案伺服器的代理伺服器位址。 |
| 代理密碼 | 選填。代理伺服器的密碼。 |
| 代理埠 | 代理伺服器的埠。 預設值為 8080。 |
| 代理用戶名 | 選填。代理伺服器的用戶名。 |

以下是[!DNL Log Processing.cfg]檔案中定義的[!DNL Log Server]的示例。 Log Source #1是指向名為FSU01的電腦上名為Logs的目錄（注意在Log Paths參數中指定的URI）的LogFile源。

![](assets/cfg_LogProcessing_LogServer.png)

## 編輯檔案伺服器單元{#section-b4a54b591b4e4435a728a67f194057ef}的權限

在上一個程式中，您為指定資料集設定了一個設定檔，以從FSU讀取記錄檔。 現在，您必須編輯FSU的權限，以允許來自執行設定檔之DPU的連線。 下列步驟將引導您完成權限檔案[!DNL Access Control.cfg]的編輯。

**編輯FSU權限的方式**

1. 開啟您要設定為FSU的Data Workbench伺服器電腦的[!DNL Server Files Manager]，然後按一下&#x200B;**[!UICONTROL Access Control]**&#x200B;以顯示其內容。

   有關開啟和使用[!DNL Server Files Manager]的資訊，請參閱&#x200B;*Data Workbench使用手冊*。

1. 在[!DNL Server Files Manager]視窗中，按一下&#x200B;**[!UICONTROL Access Control]**&#x200B;以顯示其內容。 [!DNL Access Control.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Access Control.cfg]的伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Access Control.cfg]的[!DNL Temp]列中出現複選標籤。

1. 按一下右鍵[!DNL Temp]列下新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Workstation]**。

1. 在[!DNL Access Control]視窗中，按一下&#x200B;**[!UICONTROL Access Control Groups]**&#x200B;以顯示其內容。

1. 在清單中按一下右鍵最終[!DNL AccessGroup]的數值標籤，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Group]**。

1. 輸入新[!DNL AccessGroup]的[!DNL Name]。 範例：連接伺服器。

1. 按一下右鍵新[!DNL AccessGroup]下的&#x200B;**[!UICONTROL Member]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Member]**。

1. 輸入Data Workbench伺服器（連線至此檔案伺服器）DPU的IP位址。
1. 對於連線至此FSU的任何其他Data Workbench伺服器DPU，包括必須存取記錄檔的叢集中的Data Workbench伺服器DPU，重複步驟4和5。
1. 按一下右鍵新[!DNL AccessGroup]下的&#x200B;**[!UICONTROL Read-Only Access]**，然後按一下&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL URI]**。

1. 輸入儲存的日誌檔案在檔案伺服器電腦上的位置。 在路徑規範中使用正斜線(/)。 預設位置為/Logs/。
1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**。

1. 在[!DNL Server Files Manager]視窗中，以滑鼠右鍵按一下[!DNL Temp]欄中[!DNL Access Control.cfg]的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL server name]**，將本機所做的變更儲存至Data Workbench伺服器的FSU。

## 指定日誌檔案{#section-f9a649bf1b2544feb10ad8820384edb0}的位置

必須在FSU上編輯[!DNL Communications.cfg]檔案，以指定日誌檔案的位置。

**指定日誌檔案的位置**

1. 在[!DNL Server Files Manager]視窗中，按一下&#x200B;**[!UICONTROL Components]**&#x200B;以顯示其內容。 [!DNL Communications.cfg]檔案位於此目錄中。

1. 按一下右鍵[!DNL Communications.cfg]的伺服器名稱列中的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 在[!DNL Communications.cfg]的[!DNL Temp]列中出現複選標籤。

1. 按一下右鍵[!DNL Temp]列下新建的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**。

1. 在[!DNL Communications.cfg]視窗中，按一下&#x200B;**[!UICONTROL component]**&#x200B;以顯示其內容。

1. 在[!DNL Communications.cfg]視窗中，按一下&#x200B;**[!UICONTROL Servers]**&#x200B;以顯示其內容。 可能會出現數個伺服器：檔案伺服器、日誌伺服器、初始化伺服器、狀態伺服器、發送伺服器或複製伺服器。

1. （僅適用於[!DNL Sensor]記錄來源）尋找[!DNL LoggingServer]，也就是[!DNL Sensor]寫入其要由Data Workbench伺服器處理的記錄檔的位置，然後按一下其編號以檢視功能表。 編輯日誌目錄參數以反映日誌檔案的所需位置。 預設的記錄目錄是Data Workbench伺服器安裝目錄內的記錄檔資料夾。

   請勿修改[!DNL LoggingServer]的任何其他參數。

   ![](assets/cfg_Communications_LoggingServer.png)

1. 查找指定日誌檔案位置的FileServer。 「伺服器」下可能列出了多個檔案伺服器，因此您可能需要查看其中許多伺服器的內容（通過按一下伺服器號）以找到所需的伺服器。
1. 編輯FileServer的[!DNL Local Path]和URI參數以反映日誌檔案的位置。 下列範例顯示記錄檔位於Data Workbench伺服器安裝目錄的「記錄檔」資料夾中：

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >如果[!DNL Local Path]和URI參數已如所示填入，您可以按一下[!DNL Server Files Manager]中的[!DNL Logs]，從任何Data Workbench伺服器存取FSU上的記錄檔。

1. 按一下右鍵配置窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**。

1. 在[!DNL Server Files Manager]視窗中，以滑鼠右鍵按一下[!DNL Temp]欄中[!DNL Communications.cfg]的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***，將本機所做的變更儲存至Data Workbench伺服器的FSU。

## 為群集{#section-2c1f57b683f94cc193bc069e886bba28}建立集中化標準化伺服器

如果您要將資料集設定檔設定為在Data Workbench伺服器叢集上執行，則應將叢集的FSU設為建立設定檔所有維度的伺服器。

Adobe強烈建議群集的FSU作為群集的主伺服器及其集中標準化伺服器。

要使FSU成為集中標準化伺服器，必須開啟並編輯FSU上的[!DNL Communications.cfg]和[!DNL Cluster.cfg]檔案。

**使FSU成為集中標準化伺服器**

1. 將[!DNL NormalizeServer]項目新增至FSU上的[!DNL Communications.cfg]檔案。

   >[!NOTE]
   >
   >若您已安裝Data Workbench伺服器5.0版或更新版本的完整發行套件，FSU上的[!DNL Communications.cfg]檔案應已包含[!DNL NormalizeServer]項目。 您可以依照下列步驟確認項目存在。

   1. 按照[指定記錄檔的位置](#section-f9a649bf1b2544feb10ad8820384edb0)中所述，在Data Workbench中開啟[!DNL Communications.cfg]檔案。

   1. 按一下&#x200B;**[!UICONTROL component]**&#x200B;以顯示其內容。
   1. 按一下右鍵&#x200B;**[!UICONTROL Servers]**，然後按一下&#x200B;**[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**。

   1. 在[!DNL NormalizeServer]的URI參數中，鍵入[!DNL /Cluster/]。

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. 按一下右鍵窗口頂部的&#x200B;**[!UICONTROL (modified)]**，然後按一下&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Server Files Manager]視窗中，以滑鼠右鍵按一下[!DNL Temp]欄中[!DNL Communications.cfg]的勾號，然後按一下&#x200B;**[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>*&#x200B;名稱，將本機所做的變更儲存至Data Workbench伺服器FSU。

1. 在Data Workbench伺服器叢集之主伺服器的[!DNL Cluster.cfg]檔案中，定義集中標準化伺服器。

   >[!NOTE]
   >
   >如果您要設定集中標準化伺服器的FSU不是叢集中的主資料工作台伺服器，則必須將叢集中DPU的IP位址新增至FSU [!DNL Access Control.cfg]檔案中的[!DNL Cluster Servers]存取群組。 有關將伺服器添加到[!DNL Cluster Servers]組的說明，請參閱&#x200B;*伺服器產品安裝和管理指南中的更新群集的訪問控制檔案部分。*

   1. 開啟資料集設定檔中的[!DNL Profile Manager]，然後按一下&#x200B;**[!UICONTROL Dataset]**&#x200B;以顯示其內容。 [!DNL Cluster.cfg]檔案位於此目錄中。

   1. 按一下右鍵[!DNL Cluster.cfg]旁的複選標籤，然後按一下&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中將顯示此檔案的複選標籤。

   1. 按一下右鍵新建立的複選標籤，然後按一下&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。

   1. 新增以下檔案片段中醒目提示的文字：

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >當您為SSL伺服器公共名稱參數輸入公共名稱FSU時，FSU將使用其[!DNL .address]檔案來解析公共名稱。 有關[!DNL .address]檔案的資訊，請參閱&#x200B;*伺服器產品安裝和管理指南*。

   1. 儲存檔案。
   1. 在[!DNL Profile Manager]中，以滑鼠右鍵按一下[!DNL User]欄中的[!DNL Cluster.cfg]核取記號，然後按一下&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]***&#x200B;以儲存對資料集設定檔進行的本機變更。
