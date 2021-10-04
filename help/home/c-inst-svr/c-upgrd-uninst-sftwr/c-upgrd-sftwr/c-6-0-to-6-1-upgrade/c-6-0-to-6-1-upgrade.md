---
description: 請依照下列步驟，從您的data workbench v6.0x安裝更新至data workbench v6.1。
title: Data Workbench 6.0 升級至 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Data Workbench 6.0 升級至 6.1{#data-workbench-to-upgrade}

請依照下列步驟，從您的data workbench v6.0x安裝更新至data workbench v6.1。

**步驟1**: [伺服器升級](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**步驟2**: [報表伺服器升級](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**步驟3**: [用戶端升級](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>伺服器、報表伺服器和用戶端元件已升級，可在64位元Windows作業系統上執行。

## 伺服器升級 {#section-7845393f76214aa7ad53ac4b2cca9e5b}

請依照下列步驟更新&#x200B;**[!UICONTROL Server v6.1]**&#x200B;元件：

1. 使用&#x200B;**[!UICONTROL Software and Docs]**&#x200B;設定檔，開啟&#x200B;**[!UICONTROL Start Here]**&#x200B;工作區，並將所有需要的伺服器套件下載至本機資料夾。

   * 下載&#x200B;**[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip資料夾並解壓縮所有檔案。

      伺服器包包含&#x200B;**[!UICONTROL Lookup]**&#x200B;和&#x200B;**[!UICONTROL Profile]**&#x200B;資料夾，其中包含&#x200B;**[!UICONTROL Base]**&#x200B;和&#x200B;**[!UICONTROL Transform]**&#x200B;配置檔案以更新伺服器。

      * 下載&#x200B;**[!UICONTROL Profiles]**&#x200B;資料夾。
      * 下載&#x200B;**[!UICONTROL Lookup]**&#x200B;資料夾。
      * 下載&#x200B;**[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]**&#x200B;套件。
      * 視需要下載其他&#x200B;**[!UICONTROL Sensor]**、**[!UICONTROL Documentation]**&#x200B;和&#x200B;**[!UICONTROL Dashboard]**&#x200B;檔案。

1. 停止&#x200B;**[!UICONTROL Adobe Insight Server]**&#x200B;服務。

   ![](assets/install_server_download1.png)

1. 從下載的&#x200B;**[!UICONTROL Server]**&#x200B;包：

   1. 更換[!DNL Server\Bin]資料夾以更新[!DNL InsightServer64.exe]和支援檔案。

   1. 更換[!DNL Server\Profiles]資料夾。 您可以覆寫所有檔案。
   1. 更新[!DNL Server\Lookups]資料夾。 您會想要將新下載的檔案新增至資料夾中已有的自訂檔案。
   1. 更換[!DNL Server\Software]資料夾以更新[!DNL Insight.exe]和[!DNL ReportServer.exe]
   1. 更新[!DNL Server\Scripts]資料夾以更新[!DNL TnTSend.exe]。

1. 若您採用&#x200B;**[!UICONTROL DeviceAtlas]**，則需要[更新[!DNL Server\Lookups]資料夾中的套件](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md)。

1. 設定[!DNL Profile.cfg]檔案，確保向量已更新，以反映每個設定檔的項目數。

   例如，要啟用&#x200B;**[!UICONTROL Predictive Analytics]**&#x200B;配置檔案，您需要更新此設定。

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. 為Predictive Analytics功能配置並保存PAServer.cfg檔案。

   如果您想要將預測性Analytics作業提交至伺服器，則需要設定[!DNL Server > Predictive Analytics > Dataset > PAServer.cfg]檔案以管理伺服器端叢集提交。

   自訂設定檔應繼承預測性分析設定檔的設定，允許您根據網站的實施來設定並儲存[!DNL PAServer.cfg]檔案。

1. 定義 **[!UICONTROL Log Source ID]**.

   **[!UICONTROL Recording of Rows per Log Source]**&#x200B;已新增至&#x200B;**[!UICONTROL v6.04]**，並透過新增唯一名稱&#x200B;**[!UICONTROL Log Source ID]**，定義於自訂設定檔的[!DNL Log Processing.cfg]檔案中。

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   如果您未定義記錄來源ID，則會出現下列錯誤：

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. 由於[!DNL EventMessages.dll]已更新，因此需要註銷並在群集中註冊&#x200B;**[!UICONTROL Adobe Insight Server]**。

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. 啟動群集上的&#x200B;**[!UICONTROL Adobe Insight Server]**&#x200B;服務。

伺服器安裝現已完成。

## 報表伺服器升級 {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>升級到&#x200B;**[!UICONTROL Report Server v6.1]**&#x200B;之前，必須先升級到&#x200B;**[!UICONTROL Server v6.1]**。

1. 使用&#x200B;**[!UICONTROL Software and Docs]**&#x200B;配置檔案，從&#x200B;**[!UICONTROL Report Server]**&#x200B;包下載&#x200B;**[!UICONTROL v6.1]**&#x200B;到本地資料夾。

1. 從下載的包複製&#x200B;**[!UICONTROL Report Server 6.1]**&#x200B;並替換配置檔案包。

   >[!NOTE]
   >
   >[!DNL install]資料夾中的[!DNL Insight.zbin]檔案是用於本地化的備份檔案，必須存在於[!DNL install]目錄中。 根據啟動時傳遞的命令行設定，將使用此檔案或其他[!DNL .zbin]檔案。

1. （選用）Data Workbench目前支援英文(-en-us)和中文(-zh-cn)。 您需要設定字型以支援單位元組和雙位元組字元：

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Windows作業系統還必須安裝列出的字型。

1. 為本地化配置[!DNL Report Server v6.1]。

   1. 停止&#x200B;**[!UICONTROL Adobe Insight Report Server]**&#x200B;服務。
   1. 以「管理員」的形式啟動命令提示。
   1. 導覽至報表伺服器[!DNL install]資料夾。
   1. 使用下列命令刪除報表伺服器服務：

      ```
      ReportServer.exe /unregserver
      ```

   1. 根據語言設定啟動服務：

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. 若要驗證報表伺服器是否以正確的設定執行，請開啟&#x200B;**[!UICONTROL Windows Service Manager]**&#x200B;並按一下右鍵&#x200B;**[!UICONTROL Adobe Insight Report Server - Properties]**。 執行檔的路徑將顯示更新的命令列設定。

報表伺服器安裝現已完成。

## 客戶端升級 {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>升級到&#x200B;**[!UICONTROL Client v6.1]**&#x200B;之前，管理員必須先升級到&#x200B;**[!UICONTROL Insight Server v6.1.]**

1. 啟動[!DNL Insight.exe]，但不連線至任何設定檔。
1. 編輯[!DNL Insight.cfg]檔案。

   ```
   Update Software = bool: true
   ```

1. 連線至您的設定檔。

   允許客戶端與伺服器同步，並且您的客戶端將升級為最新的v6.1客戶端配置檔案、執行檔和配置檔案。

   >[!NOTE]
   >
   >[!DNL install]資料夾中的[!DNL Insight.zbin]檔案是用於本地化的備份檔案，必須存在。 根據啟動時傳遞的命令行設定，將使用此檔案或其他[!DNL .zbin]檔案。

   請參閱[設定本地化語言](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e)以添加本地化設定所需的[!DNL insight.zbin]檔案。

**其他客戶端設定**

配置[!DNL Insight.exe]和支援檔案之前，必須退出客戶端應用程式。

安裝簡體中文：

1. 建立快捷方式，該快捷方式將命令行設定傳遞至[!DNL Insight.exe]檔案。

   ```
   Insight.exe -zh-cn
   ```

1. 配置[!DNL Insight.cfg]以支援單位元組和雙位元組字型字元。

   Data Workbench目前支援英文和簡體中文。 您可以選取字型以支援以下兩種語言：

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

   Windows作業系統還必須安裝所請求的字型。

1. 啟動您建立用來同步設定檔和更新的快速鍵。 [!DNL zbin] 檔案。

使用輸入法編輯器(IME)。

IME允許輸入國際字元。

1. 使用以下設定更新[!DNL Insight.cfg]檔案：

   ```
   Localized IME = bool: true
   ```

1. 啟動您為同步配置檔案和更新的[!DNL .zbin]檔案而建立的快捷方式。

客戶端安裝現在已完成。
