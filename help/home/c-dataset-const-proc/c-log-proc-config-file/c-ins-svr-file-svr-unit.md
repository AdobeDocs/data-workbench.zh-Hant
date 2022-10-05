---
description: 有關Insight Server檔案伺服器單元和檔案伺服器設定程式的資訊。
title: 設定 Data Workbench 伺服器檔案伺服器單元
uuid: ccb65952-f017-4434-b2f8-74c274450834
exl-id: 19b8c08a-e9f2-47ab-ad9f-1fddfbd9d249
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1784'
ht-degree: 1%

---

# 設定 Data Workbench 伺服器檔案伺服器單元{#configuring-a-data-workbench-server-file-server-unit}

{{eol}}

有關Insight Server檔案伺服器單元和檔案伺服器設定程式的資訊。

<!--
c_abt_file_svr_units.xml
-->

您可以完成以下變數中的參數，將Data Workbench伺服器(InsightServer64.exe)設定為以檔案伺服器單元(FSU)的形式執行： **[!UICONTROL Log Sources]** > **[!UICONTROL Log Server]** 節點 [!DNL Log Processing.cfg] 檔案。 當Data Workbench伺服器設定為以FSU執行時，會儲存來源檔案( [!DNL .vsl] 檔案、文字檔案或XML檔案)，這些檔案可由多個處理伺服器(DPU)快速存取。 當Data Workbench伺服器叢集中的DPU存取FSU以讀取記錄檔時，會將記錄檔分割，並保證不會多次處理相同的檔案。

>[!NOTE]
>
>設定提供Data Workbench伺服器叢集（由5到10個DPU組成）的FSU時，應將叢集的主伺服器設為FSU。

如需安裝Data Workbench伺服器叢集的相關資訊，請參閱 *《伺服器產品安裝與管理指南》*.

<!--
c_file_svr_config_proc.xml
-->

如果位置是遠端位置，則處理資料的Data Workbench伺服器電腦會連線至指定的遠端電腦以讀取記錄檔。

在指定為FSU的Data Workbench伺服器電腦上， [!DNL Access Control.cfg] 檔案可讓DPU連線至FSU，而 [!DNL Communications.cfg] 檔案映射遠程資料檔案的位置。 配置FSU的流程步驟如下：

1. 在 [!DNL Log Processing.cfg] 檔案，請指定資料來源的類型和來源的位置。 請參閱 [指定資料源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-d2b545db7ab142ffb4be32e040395383).

1. 在 [!DNL Access Control.cfg] 檔案，編輯權限以允許DPU連線至FSU以讀取記錄檔資料。 請參閱 [編輯檔案伺服器單元的權限](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-b4a54b591b4e4435a728a67f194057ef).

1. 在 [!DNL Communications.cfg] 檔案，編輯 [!DNL LoggingServer] 和 [!DNL FileServer] 指定日誌檔案位置的條目。 請參閱 [指定日誌檔案的位置](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-f9a649bf1b2544feb10ad8820384edb0).

1. 如果您要將資料集設定檔設定為在Data Workbench伺服器叢集上執行，您也必須將叢集的FSU設為建構所有設定檔維度的伺服器：（僅適用於Data Workbench伺服器叢集） [!DNL Communications.cfg] 和 [!DNL cluster.cfg] FSU上的檔案，添加「標準化伺服器」條目，使FSU成為構建所有維的群集內的伺服器。 請參閱 [為群集建立集中標準化伺服器](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#section-2c1f57b683f94cc193bc069e886bba28).

如需設定要由Data Workbench伺服器叢集處理的資料集設定檔的指示，請參閱 *《伺服器產品安裝與管理指南》*.

>[!NOTE]
>
>以下說明假設所有日誌檔案都位於預設目錄中。 如果您想要將記錄檔儲存在其他目錄中或建立多個記錄路徑，請聯絡Adobe諮詢服務以討論您的特定設定。

## 指定資料源 {#section-d2b545db7ab142ffb4be32e040395383}

指定資料集的遠端資料來源時，您必須指定資料來源類型和主資料工作台伺服器上記錄檔的位置。

**指定資料源及其位置**

1. 開啟 [!DNL Log Processing.cfg] 檔案. 請參閱 [編輯記錄處理組態檔](../../../home/c-dataset-const-proc/c-log-proc-config-file/t-edit-log-proc-config-file.md#task-6a2fa1b735cb4eefad730f0a3a7858e5).

1. 新增 [!DNL Sensor]、日誌檔案或XML資料源。 請參閱 [記錄檔](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e).

1. 完成Log Paths參數。 請參閱 [感測器檔案](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-b25f11c477b54032a15b6117b3bf9009), [記錄檔](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e)，或 [XML日誌源](../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-c7b154e93748447b986e97f6ef688887). 請務必指定有效的URI。

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
   <td colname="col2"> <p> <span class="wintitle"> 伺服器公用名</span> 列在檔案伺服器的SSL憑證上。 </p> <p> 若 <span class="wintitle"> 使用SSL</span> 設為false時，退出連結才會受到追蹤。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 地址 </td> 
   <td colname="col2"> <p>檔案伺服器電腦的地址。 若 <span class="wintitle"> 名稱</span> matches <span class="wintitle"> SSL伺服器公用名稱</span>. </p> <p> 例如： <span class="filepath"> visual.mycompany.com</span> 或192.168.1.90。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 埠 </td> 
   <td colname="col2"> Data Workbench伺服器電腦與檔案伺服器通訊的埠。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> SSL用戶端憑證 </td> 
   <td colname="col2"> 名稱 <span class="wintitle"> SSL憑證</span> data workbench伺服器的檔案(<span class="filepath"> server_cert.pem</span>)。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 使用SSL </td> 
   <td colname="col2"> True或False。 True表示檔案伺服器使用 <span class="wintitle"> SSL</span>. </td> 
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

以下是已定義 [!DNL Log Server] 在 [!DNL Log Processing.cfg] 檔案。 Log Source #1是指向名為FSU01的電腦上名為Logs的目錄（注意在Log Paths參數中指定的URI）的LogFile源。

![](assets/cfg_LogProcessing_LogServer.png)

## 編輯檔案伺服器單元的權限 {#section-b4a54b591b4e4435a728a67f194057ef}

在上一個程式中，您為指定資料集設定了一個設定檔，以從FSU讀取記錄檔。 現在，您必須編輯FSU的權限，以允許來自執行設定檔之DPU的連線。 下列步驟將引導您完成權限檔案的編輯 [!DNL Access Control.cfg].

**編輯FSU權限的方式**

1. 開啟 [!DNL Server Files Manager] 針對您要設定為FSU的資料工作台伺服器電腦，按一下 **[!UICONTROL Access Control]** 來顯示其內容。

   如需開啟和使用的相關資訊 [!DNL Server Files Manager]，請參閱 *Data Workbench使用手冊*.

1. 在 [!DNL Server Files Manager] 按一下 **[!UICONTROL Access Control]** 來顯示其內容。 此 [!DNL Access Control.cfg] 檔案位於此目錄中。

1. 按一下右鍵伺服器名稱列中的複選標籤， [!DNL Access Control.cfg]，然後按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Access Control.cfg].

1. 按一下右鍵新建立的複選標籤(位於 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. 在 [!DNL Access Control] 按一下 **[!UICONTROL Access Control Groups]** 來顯示其內容。

1. 以滑鼠右鍵按一下最終版本的數值標籤 [!DNL AccessGroup] 按一下 **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

1. 輸入 [!DNL Name] 新 [!DNL AccessGroup]. 範例：連接伺服器。

1. 按一下右鍵 **[!UICONTROL Member]** 新 [!DNL AccessGroup]，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. 輸入Data Workbench伺服器（連線至此檔案伺服器）DPU的IP位址。
1. 對於連線至此FSU的任何其他Data Workbench伺服器DPU，包括必須存取記錄檔的叢集中的Data Workbench伺服器DPU，重複步驟4和5。
1. 按一下右鍵 **[!UICONTROL Read-Only Access]** 新 [!DNL AccessGroup]，然後按一下 **[!UICONTROL Add new]** > **[!UICONTROL URI]**.

1. 輸入儲存的日誌檔案在檔案伺服器電腦上的位置。 在路徑規範中使用正斜線(/)。 預設位置為/Logs/。
1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端，按一下 **[!UICONTROL Save]**.

1. 在 [!DNL Server Files Manager] 按一下右鍵 [!DNL Access Control.cfg] 在 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** > **[!UICONTROL server name]** 將本機所做的變更儲存至data workbench伺服器的FSU。

## 指定日誌檔案的位置 {#section-f9a649bf1b2544feb10ad8820384edb0}

您必須編輯 [!DNL Communications.cfg] 檔案，以指定記錄檔的位置。

**指定日誌檔案的位置**

1. 在 [!DNL Server Files Manager] 按一下 **[!UICONTROL Components]** 來顯示其內容。 此 [!DNL Communications.cfg] 檔案位於此目錄中。

1. 按一下右鍵伺服器名稱列中的複選標籤， [!DNL Communications.cfg]，然後按一下 **[!UICONTROL Make Local]**. 勾號會出現在 [!DNL Temp] 欄 [!DNL Communications.cfg].

1. 按一下右鍵新建立的複選標籤(位於 [!DNL Temp] 欄，按一下 **[!UICONTROL Open]** > **[!UICONTROL in Workstation.]**.

1. 在 [!DNL Communications.cfg] 按一下 **[!UICONTROL component]** 來顯示其內容。

1. 在 [!DNL Communications.cfg] 按一下 **[!UICONTROL Servers]** 來顯示其內容。 可能會出現數個伺服器：檔案伺服器、日誌伺服器、初始化伺服器、狀態伺服器、發送伺服器或複製伺服器。

1. (適用於 [!DNL Sensor] 僅日誌源)查找 [!DNL LoggingServer]，其中 [!DNL Sensor] 寫入要由data workbench伺服器處理的記錄檔，然後按一下其編號以檢視功能表。 編輯日誌目錄參數以反映日誌檔案的所需位置。 預設的記錄目錄是Data Workbench伺服器安裝目錄內的記錄檔資料夾。

   請勿修改 [!DNL LoggingServer].

   ![](assets/cfg_Communications_LoggingServer.png)

1. 查找指定日誌檔案位置的FileServer。 「伺服器」下可能列出了多個檔案伺服器，因此您可能需要查看其中許多伺服器的內容（通過按一下伺服器號）以找到所需的伺服器。
1. 編輯 [!DNL Local Path] 和URI參數，以反映日誌檔案的位置。 下列範例顯示記錄檔位於Data Workbench伺服器安裝目錄的「記錄檔」資料夾中：

   ![](assets/cfg_Communications_FS.png)

   >[!NOTE]
   >
   >若 [!DNL Local Path] 和URI參數會如所示填入，您可以按一下，從任何Data Workbench伺服器存取FSU上的記錄檔 [!DNL Logs] 在 [!DNL Server Files Manager].

1. 按一下右鍵 **[!UICONTROL (modified)]** 在設定視窗頂端，按一下 **[!UICONTROL Save]**.

1. 在 [!DNL Server Files Manager] 按一下右鍵 [!DNL Communications.cfg] 在 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>* 將本機所做的變更儲存至data workbench伺服器的FSU。

## 為群集建立集中標準化伺服器 {#section-2c1f57b683f94cc193bc069e886bba28}

如果您要將資料集設定檔設定為在Data Workbench伺服器叢集上執行，則應將叢集的FSU設為建立設定檔所有維度的伺服器。

Adobe強烈建議群集的FSU作為群集的主伺服器及其集中標準化伺服器。

要使FSU成為集中標準化伺服器，必須開啟和編輯 [!DNL Communications.cfg] 和 [!DNL Cluster.cfg] 檔案。

**使FSU成為集中標準化伺服器**

1. 新增 [!DNL NormalizeServer] 的 [!DNL Communications.cfg] 檔案。

   >[!NOTE]
   >
   >若您已安裝Data Workbench伺服器5.0版或更新版本的完整發行套件，則 [!DNL Communications.cfg] FSU上的檔案應該有 [!DNL NormalizeServer] 條目。 您可以依照下列步驟確認項目存在。

   1. 開啟 [!DNL Communications.cfg] 資料工作台中的檔案，如 [指定日誌檔案的位置](#section-f9a649bf1b2544feb10ad8820384edb0).

   1. 按一下 **[!UICONTROL component]** 來顯示其內容。
   1. 按一下右鍵 **[!UICONTROL Servers]** 按一下 **[!UICONTROL Add New]** > **[!UICONTROL Centralized Normalization Server]**.

   1. 在 [!DNL NormalizeServer]，類型 [!DNL /Cluster/].

      ![](assets/cfg_Communications_NormalizeServer.png)

   1. 按一下右鍵 **[!UICONTROL (modified)]** 在視窗頂端，按一下 **[!UICONTROL Save]**.

   1. 在 [!DNL Server Files Manager] 按一下右鍵 [!DNL Communications.cfg] 在 [!DNL Temp] 欄，然後按一下 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server]**>* 名稱，將本機所做的變更儲存至data workbench伺服器FSU。

1. 在 [!DNL Cluster.cfg] 檔案。

   >[!NOTE]
   >
   >如果您要設定集中標準化伺服器的FSU不是叢集中的主資料工作台伺服器，則您必須將叢集中DPU的IP位址新增至 [!DNL Cluster Servers] FSU中的訪問組 [!DNL Access Control.cfg] 檔案。 如需將伺服器新增至 [!DNL Cluster Servers] 組，請參閱更新群集的「訪問控制檔案」部分(位於 *《伺服器產品安裝與管理指南》。*

   1. 開啟 [!DNL Profile Manager] 在資料集設定檔中，按一下 **[!UICONTROL Dataset]** 來顯示其內容。 此 [!DNL Cluster.cfg] 檔案位於此目錄中。

   1. 以滑鼠右鍵按一下旁的核取記號 [!DNL Cluster.cfg]，然後按一下 **[!UICONTROL Make Local]**. 此檔案的複選標籤會顯示在 [!DNL User] 欄。

   1. 按一下右鍵新建立的複選標籤，然後按一下 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.

   1. 新增以下檔案片段中醒目提示的文字：

      [!DNL Cluster = ClusterConfig:]

      [!DNL Normalize Server = serverInfo:]

      [!DNL Address = string:]

      [!DNL Port = int: 80]

      [!DNL SSL Server Common Name = string: server common name]

      [!DNL Use SSL = bool: false]

      >[!NOTE]
      >
      >當您為SSL伺服器公用名稱參數輸入公用名稱FSU時，FSU會使用其 [!DNL .address] 檔案來解析通用名稱。 如需 [!DNL .address] 檔案，請參閱 *《伺服器產品安裝與管理指南》*.

   1. 儲存檔案。
   1. 在 [!DNL Profile Manager]，按一下右鍵的複選標籤 [!DNL Cluster.cfg] 在 [!DNL User] 欄，然後按一下 **[!UICONTROL Save to]** > ***[!UICONTROL dataset profile name]*** 將本機對資料集設定檔進行的變更儲存。
