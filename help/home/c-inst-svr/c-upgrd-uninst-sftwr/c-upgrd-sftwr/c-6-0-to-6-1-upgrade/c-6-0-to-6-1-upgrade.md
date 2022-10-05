---
description: 請依照下列步驟，從您的data workbench v6.0x安裝更新至data workbench v6.1。
title: Data Workbench 6.0 升級至 6.1
uuid: 4671c2bf-06ab-49c4-8dd1-24115facd83b
exl-id: 559e1942-561c-4270-9670-550177730cdb,2a337d2e-c70e-4f35-a6c2-c3a7f50a0800
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 1%

---

# Data Workbench 6.0 升級至 6.1{#data-workbench-to-upgrade}

{{eol}}

請依照下列步驟，從您的data workbench v6.0x安裝更新至data workbench v6.1。

**步驟1**: [伺服器升級](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-7845393f76214aa7ad53ac4b2cca9e5b)

**步驟2**: [報表伺服器升級](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**步驟3**: [用戶端升級](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-6-0-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>伺服器、報表伺服器和用戶端元件已升級，可在64位元Windows作業系統上執行。

## 伺服器升級 {#section-7845393f76214aa7ad53ac4b2cca9e5b}

請依照下列步驟，更新 **[!UICONTROL Server v6.1]** 元件：

1. 使用 **[!UICONTROL Software and Docs]** 設定檔，開啟 **[!UICONTROL Start Here]** 工作區，並將所有需要的伺服器套件下載至本機資料夾。

   * 下載 **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip資料夾並解壓縮所有檔案。

      伺服器包包括 **[!UICONTROL Lookup]** 和 **[!UICONTROL Profile]** 資料夾 **[!UICONTROL Base]** 和 **[!UICONTROL Transform]** 設定檔以更新伺服器。

      * 下載 **[!UICONTROL Profiles]** 資料夾。
      * 下載 **[!UICONTROL Lookup]** 資料夾。
      * 下載 **[!UICONTROL Report Server]** \ **[!UICONTROL v6.1]** 包。
      * 下載其他 **[!UICONTROL Sensor]**, **[!UICONTROL Documentation]**，和 **[!UICONTROL Dashboard]** 檔案。

1. 停止 **[!UICONTROL Adobe Insight Server]** 服務。

   ![](assets/install_server_download1.png)

1. 從下載的 **[!UICONTROL Server]** 包：

   1. 取代 [!DNL Server\Bin] 要更新的資料夾 [!DNL InsightServer64.exe] 和支援檔案。

   1. 取代 [!DNL Server\Profiles] 檔案夾。 您可以覆寫所有檔案。
   1. 更新 [!DNL Server\Lookups] 檔案夾。 您會想要將新下載的檔案新增至資料夾中已有的自訂檔案。
   1. 取代 [!DNL Server\Software] 更新資料夾 [!DNL Insight.exe] 和 [!DNL ReportServer.exe]
   1. 更新 [!DNL Server\Scripts] 更新資料夾 [!DNL TnTSend.exe].

1. 若您採用 **[!UICONTROL DeviceAtlas]**，則您需要 [更新套件組合](/help/home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md) 位於 [!DNL Server\Lookups] 檔案夾。

1. 設定 [!DNL Profile.cfg] 檔案，確保向量已更新，以反映每個設定檔的項目數。

   例如，若要啟用 **[!UICONTROL Predictive Analytics]** 設定檔，您需要更新此設定。

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. 為Predictive Analytics功能配置並保存PAServer.cfg檔案。

   如果您想要將Predictive Analytics作業提交至伺服器，則需要設定 [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] 檔案，管理伺服器端叢集提交。

   自訂設定檔應繼承Predictive Analytics設定檔的設定，讓您可以設定並儲存 [!DNL PAServer.cfg] 檔案。

1. 定義 **[!UICONTROL Log Source ID]**.

   此 **[!UICONTROL Recording of Rows per Log Source]** 新增於 **[!UICONTROL v6.04]** 和定義於自訂設定檔的 [!DNL Log Processing.cfg] 檔案，方法是新增唯一名稱的 **[!UICONTROL Log Source ID]**.

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   如果您未定義記錄來源ID，則會出現下列錯誤：

   ```
   Missing Log Source ID in log processing.cfg.
   Log Source ID must be defined for all log sources.
   ```

1. 因為 [!DNL EventMessages.dll] 已更新，需要您註銷並註冊 **[!UICONTROL Adobe Insight Server]** 跨叢集。

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. 啟動 **[!UICONTROL Adobe Insight Server]** 服務。

伺服器安裝現已完成。

## 報表伺服器升級 {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>升級至 **[!UICONTROL Report Server v6.1]**，您必須先升級至 **[!UICONTROL Server v6.1]**.

1. 使用 **[!UICONTROL Software and Docs]** 設定檔，下載 **[!UICONTROL v6.1]** 從 **[!UICONTROL Report Server]** 封裝至本機資料夾。

1. 複製 **[!UICONTROL Report Server 6.1]** 從下載的套件中取代設定檔套件。

   >[!NOTE]
   >
   >此 [!DNL Insight.zbin] 檔案 [!DNL install] 資料夾是用於本地化的備份檔案，必須存在於 [!DNL install] 目錄。 此檔案或其他 [!DNL .zbin] 會根據啟動時傳遞的命令列設定來使用檔案。

1. （選用）Data Workbench目前支援英文(-en-us)和中文(-zh-cn)。 您需要設定字型以支援單位元組和雙位元組字元：

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Windows作業系統還必須安裝列出的字型。

1. 設定 [!DNL Report Server v6.1] 本地化。

   1. 停止 **[!UICONTROL Adobe Insight Report Server]** 服務。
   1. 以「管理員」的形式啟動命令提示。
   1. 導覽至報表伺服器 [!DNL install] 檔案夾。
   1. 使用下列命令刪除報表伺服器服務：

      ```
      ReportServer.exe /unregserver
      ```

   1. 根據語言設定啟動服務：

      ```
      ReportServer.exe -RegServer -Locale -en-us (English)
      ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
      ```

1. 若要驗證報表伺服器是否以正確的設定執行，請開啟 **[!UICONTROL Windows Service Manager]** 並按一下滑鼠右鍵 **[!UICONTROL Adobe Insight Report Server - Properties]**. 執行檔的路徑將顯示更新的命令列設定。

報表伺服器安裝現已完成。

## 客戶端升級 {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>升級至 **[!UICONTROL Client v6.1]**，管理員必須先升級至 **[!UICONTROL Insight Server v6.1.]**

1. Launch [!DNL Insight.exe] 但請勿連線至任何設定檔。
1. 編輯 [!DNL Insight.cfg] 檔案。

   ```
   Update Software = bool: true
   ```

1. 連線至您的設定檔。

   允許客戶端與伺服器同步，並且您的客戶端將升級為最新的v6.1客戶端配置檔案、執行檔和配置檔案。

   >[!NOTE]
   >
   >此 [!DNL Insight.zbin] 檔案 [!DNL install] 資料夾是用於本地化的備份檔案，必須存在。 此檔案或其他 [!DNL .zbin] 會根據啟動時傳遞的命令列設定來使用檔案。

   請參閱 [設定本地化語言](../../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-localized-ime.md#concept-86d7602cd6ec416b8d4a518f325e001e) 若要新增 [!DNL insight.zbin] 本地化設定所需的檔案。

**其他客戶端設定**

設定前 [!DNL Insight.exe] 和支援檔案，您必須退出客戶端應用程式。

安裝簡體中文：

1. 建立快捷方式，該快捷方式將命令行設定中的 [!DNL Insight.exe] 檔案。

   ```
   Insight.exe -zh-cn
   ```

1. 設定 [!DNL Insight.cfg] 支援單位元組和雙位元組字型字元。

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

1. 更新 [!DNL Insight.cfg] 具有下列設定的檔案：

   ```
   Localized IME = bool: true
   ```

1. 啟動您建立用來同步設定檔和更新的 [!DNL .zbin] 檔案。

客戶端安裝現在已完成。
