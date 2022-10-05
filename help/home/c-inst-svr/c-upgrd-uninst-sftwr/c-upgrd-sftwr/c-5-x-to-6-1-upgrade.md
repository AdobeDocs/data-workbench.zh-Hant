---
description: 請依照下列步驟，從Insight v5.5x安裝更新至data workbench v6.1。
title: Data Workbench 5.5 升級至 6.1
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---

# Data Workbench 5.5 升級至 6.1{#data-workbench-to-upgrade}

{{eol}}

請依照下列步驟，從Insight v5.5x安裝更新至data workbench v6.1。

**步驟1**: [伺服器升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**步驟2**: [報表伺服器升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**步驟3**: [客戶端升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>伺服器、報表伺服器和用戶端元件已升級，可在64位元Windows作業系統上執行。

## 伺服器升級 {#section-08bd6fe3da8740fcb19688e8cac6f223}

請依照下列步驟，更新 **[!UICONTROL Server v6.1]** 元件：

1. 使用 **[!UICONTROL Software and Docs]** 設定檔，開啟 **[!UICONTROL Start Here]** 工作區，並將所有需要的伺服器套件下載至本機資料夾。

   * 下載 **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip資料夾並解壓縮所有檔案。

      此 **[!UICONTROL Server]** 包含 **[!UICONTROL Lookup]** 和 **[!UICONTROL Profile]** 資料夾 **[!UICONTROL Base]** 和 **[!UICONTROL Transform]** 要添加和替換的查找檔案以更新伺服器。

   * 下載新 **[!UICONTROL Profiles]** 資料夾。
   * 已更新下載 **[!UICONTROL Lookup]** 資料夾。
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
1. 設定 [!DNL Directories] 在 [!DNL Profile.cfg] 檔案，確保向量已更新，以反映每個設定檔的項目數。

   例如，若要啟用 **[!UICONTROL Predictive Analytics]** 設定檔，您需要更新此設定。

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. 設定並儲存 [!DNL PAServer.cfg] 檔案來升級Predictive Analytics功能。

   如果您想要將Predictive Analytics作業提交至伺服器，則需要設定 [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] 檔案，管理伺服器端叢集提交。

   自訂設定檔應繼承Predictive Analytics設定檔的設定，讓您可以設定並儲存 [!DNL PAServer.cfg] 根據您網站的實作。

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

1. （可選）修改報表伺服器設定檔案以支援雙位元組字元。

   Data Workbench目前支援英文(-en-us)和中文(-zh-cn)。 您需要設定字型以支援單位元組和雙位元組字元：

   ```
   Report Server.cfg - Add Fonts
      Fonts = vector: 2 items
      0 = string: SimSun
      1 = string: Arial
   ```

   Windows作業系統還必須安裝列出的字型。

1. 設定 [!DNL Report Server v6.1].

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
>升級至 **[!UICONTROL Client v6.1]**，管理員必須先升級至 **[!UICONTROL Server v6.1.]**

1. Launch [!DNL Insight.exe] 但請勿連線至任何設定檔。
1. 編輯 [!DNL Insight.cfg] 檔案不自動更新軟體。

   ```
   Update Software = bool: false
   ```

1. 連線至 **[!UICONTROL Software and Docs]** 配置檔案（軟體文檔）。
1. 下載 [!DNL Software\Insight Client\v6.10].
1. （可選）修改 [!DNL insight.cfg] 以支援雙位元組字元。

   Data Workbench目前支援英文和簡體中文。 選擇字型以支援以下兩種語言：

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

1. 退出客戶端。
1. 複製下載檔案中的檔案 **v6.1** 客戶端包 [!DNL Install] 檔案夾。

   >[!NOTE]
   >
   >此 [!DNL Insight.zbin] 「安裝」資料夾中的檔案是用於本地化的備份檔案，必須位於「安裝」目錄中。 此檔案或其他 [!DNL .zbin] 會根據啟動時傳遞的命令列設定來使用檔案。
   >
   >例如，要啟動「簡體中文」，請建立在命令行設定中傳遞的快捷方式。
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >如果您想要以英文（預設）啟動，則不需要變更命令列。

1. Launch [!DNL Insight.exe] ，或您為其他語言建立的捷徑。
1. 連接到您的配置檔案，並允許客戶端與伺服器同步。
1. （可選）若要使用IME，請對 [!DNL Insight.cfg] 檔案：

   ```
   Localized IME = bool: true
   ```

   輸入法編輯器(IME)允許您輸入國際字元。

1. （選用）編輯 [!DNL Insight.cfg] 檔案以自動更新軟體：

   ```
   Update Software = bool: true
   ```

   請參閱實施IME的說明。
1. 在設定檔同步後重新啟動，以採用最新的 [!DNL .zbin] 檔案。

客戶端安裝現在已完成。
