---
description: 請依照下列步驟，從Insight v5.5x安裝更新至data workbench v6.1。
title: Data Workbench 5.5 升級至 6.1
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
exl-id: c730f6d5-2171-4d97-a967-509dc2517c86,3f25917b-b929-4e3b-84f0-1a81b30ba641
source-git-commit: b21da6d12175fa8570b1b366049baa9c8e8ea862
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 1%

---

# Data Workbench 5.5 升級至 6.1{#data-workbench-to-upgrade}

請依照下列步驟，從Insight v5.5x安裝更新至data workbench v6.1。

**步驟1**: [伺服器升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**步驟2**: [報表伺服器升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**步驟3**: [客戶端升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>伺服器、報表伺服器和用戶端元件已升級，可在64位元Windows作業系統上執行。

## 伺服器升級 {#section-08bd6fe3da8740fcb19688e8cac6f223}

請依照下列步驟更新&#x200B;**[!UICONTROL Server v6.1]**&#x200B;元件：

1. 使用&#x200B;**[!UICONTROL Software and Docs]**&#x200B;設定檔，開啟&#x200B;**[!UICONTROL Start Here]**&#x200B;工作區，並將所有需要的伺服器套件下載至本機資料夾。

   * 下載&#x200B;**[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip資料夾並解壓縮所有檔案。

      **[!UICONTROL Server]**&#x200B;套件包含&#x200B;**[!UICONTROL Lookup]**&#x200B;和&#x200B;**[!UICONTROL Profile]**&#x200B;資料夾，以及&#x200B;**[!UICONTROL Base]**&#x200B;和&#x200B;**[!UICONTROL Transform]**&#x200B;查閱檔案，以新增和取代以更新伺服器。

   * 下載新的&#x200B;**[!UICONTROL Profiles]**&#x200B;資料夾。
   * 下載更新的&#x200B;**[!UICONTROL Lookup]**&#x200B;資料夾。
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
1. 在[!DNL Profile.cfg]檔案中設定[!DNL Directories] ，以確保向量已更新，以反映每個設定檔的項目數。

   例如，要啟用&#x200B;**[!UICONTROL Predictive Analytics]**&#x200B;配置檔案，您需要更新此設定。

   ```
   Directories = vector: 5 items
       0 = string: Base\\
       1 = string: Geography\\
       2 = string: Predictive Analytics\\
       3 = string: Adobe SC\\
       4 = string: Profile Name\\
   ```

1. 設定並儲存[!DNL PAServer.cfg]檔案以升級Predictive Analytics功能。

   如果您想要將預測性Analytics作業提交至伺服器，則需要設定[!DNL Server > Predictive Analytics > Dataset > PAServer.cfg]檔案以管理伺服器端叢集提交。

   自訂設定檔應繼承預測性分析設定檔的設定，允許您根據網站的實施來設定並儲存[!DNL PAServer.cfg]。

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
>升級到&#x200B;**[!UICONTROL Client v6.1]**&#x200B;之前，管理員必須先升級到&#x200B;**[!UICONTROL Server v6.1.]**

1. 啟動[!DNL Insight.exe]但「請勿」連線至任何設定檔。
1. 編輯[!DNL Insight.cfg]檔案，不自動更新軟體。

   ```
   Update Software = bool: false
   ```

1. 連接到&#x200B;**[!UICONTROL Software and Docs]**&#x200B;配置檔案（軟體文檔）。
1. 下載 [!DNL Software\Insight Client\v6.10].
1. （可選）修改[!DNL insight.cfg]以支援雙位元組字元。

   Data Workbench目前支援英文和簡體中文。 選擇字型以支援以下兩種語言：

   ```
   Fonts = vector: 2 items
   0 = string: SimSun
   1 = string: Arial
   ```

1. 退出客戶端。
1. 將下載的&#x200B;**v6.1**&#x200B;客戶端包中的檔案複製到[!DNL Install]資料夾。

   >[!NOTE]
   >
   >安裝資料夾中的[!DNL Insight.zbin]檔案是用於本地化的備份檔案，必須位於安裝目錄中。 根據啟動時傳遞的命令行設定，將使用此檔案或其他[!DNL .zbin]檔案。
   >
   >例如，要啟動「簡體中文」，請建立在命令行設定中傳遞的快捷方式。
   >
   >
   ```
   >Insight.exe -zh-cn
   >```
   >
   >如果您想要以英文（預設）啟動，則不需要變更命令列。

1. 啟動[!DNL Insight.exe]以取得英文或您為其他語言建立的捷徑。
1. 連接到您的配置檔案，並允許客戶端與伺服器同步。
1. （可選）要採用IME，請對[!DNL Insight.cfg]檔案進行以下更改：

   ```
   Localized IME = bool: true
   ```

   輸入法編輯器(IME)允許您輸入國際字元。

1. （可選）編輯[!DNL Insight.cfg]檔案以自動更新軟體：

   ```
   Update Software = bool: true
   ```

   請參閱實施IME的說明。
1. 在配置檔案同步後重新啟動，以使用最新的[!DNL .zbin]檔案。

客戶端安裝現在已完成。
