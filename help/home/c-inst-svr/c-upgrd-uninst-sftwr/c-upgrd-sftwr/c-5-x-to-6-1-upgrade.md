---
description: 請依照下列步驟，從Insight v5.5x安裝更新至資料工作台v6.1。
solution: Analytics
title: 資料工作台5.5至6.1升級
topic: Data workbench
uuid: 14e3612e-11a2-402a-9478-904ec55df23c
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# 資料工作台5.5至6.1升級{#data-workbench-to-upgrade}

請依照下列步驟，從Insight v5.5x安裝更新至資料工作台v6.1。

**步驟1**:服 [務器升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-08bd6fe3da8740fcb19688e8cac6f223)

**步驟2**:報 [告伺服器升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-afd9560a446242e9b06490e5f98aaaec)

**步驟3**:客戶 [端升級](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-5-x-to-6-1-upgrade.md#section-c896e57ecd2847afb18f4d8ef7cc0e06)

>[!IMPORTANT]
>
>伺服器、報告伺服器和用戶端元件已升級為可在64位元Windows作業系統上執行。

## 伺服器升級 {#section-08bd6fe3da8740fcb19688e8cac6f223}

請依照下列步驟更新元 **[!UICONTROL Server v6.1]** 件：

1. 使用配 **[!UICONTROL Software and Docs]** 置檔案，開啟工 **[!UICONTROL Start Here]** 作區並將所有需要的伺服器軟體包下載到本地資料夾。

   * 下載 **[!UICONTROL Server Packages]** \ **[!UICONTROL v6.1]** zip資料夾並解壓縮所有檔案。

      此套 **[!UICONTROL Server]** 件包含 **[!UICONTROL Lookup]** 資料夾和資料夾， **[!UICONTROL Profile]** 其中包含要新增和 **[!UICONTROL Base]****[!UICONTROL Transform]** 取代以更新伺服器的查閱檔案。

   * 下載新的 **[!UICONTROL Profiles]** 資料夾。
   * 下載更新的 **[!UICONTROL Lookup]** 檔案夾。
   * 下載 **[!UICONTROL Report Server]** \包 **[!UICONTROL v6.1]** 。
   * 視需要 **[!UICONTROL Sensor]**&#x200B;下載 **[!UICONTROL Documentation]**&#x200B;其他 **[!UICONTROL Dashboard]** 、和您的系統檔案。

1. 停止服 **[!UICONTROL Adobe Insight Server]** 務。

   ![](assets/install_server_download1.png)

1. 從下載的 **[!UICONTROL Server]** 套件：

   1. 更換文 [!DNL Server\Bin] 件夾以更新和 [!DNL InsightServer64.exe] 支援檔案。

   1. 更換文 [!DNL Server\Profiles] 件夾。 您可以覆寫所有檔案。
   1. 更新資 [!DNL Server\Lookups] 料夾。 您會想要將新下載的檔案新增至資料夾中已有的自訂檔案。
   1. 更換資 [!DNL Server\Software] 料夾以更新 [!DNL Insight.exe] 及 [!DNL ReportServer.exe]

   1. 更新資 [!DNL Server\Scripts] 料夾以更新 [!DNL TnTSend.exe]。

1. 如果您採 **[!UICONTROL DeviceAtlas]**&#x200B;用，則需要更 [新位於資料夾中的搭](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/trans-config-file/c-deviceatlas-update.html)[!DNL Server\Lookups] 售。
1. 在檔 [!DNL Directories] 案中設 [!DNL Profile.cfg] 定，以確保向量已更新，以反映每個描述檔的項目數。

   例如，若要啟用描述 **[!UICONTROL Predictive Analytics]** 檔，您需要更新此設定。

   ```
   Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
       4 = string: Profile Name\\
   ```

1. 設定並儲存檔 [!DNL PAServer.cfg] 案以升級預測性分析功能。

   如果您想要將Predictive Analytics作業送出至伺服器，則需要設定檔 [!DNL Server > Predictive Analytics > Dataset > PAServer.cfg] 案以管理伺服器端叢集提交。

   自訂描述檔應繼承Predictive Analytics設定描述檔的設定，讓您根據網站的實 [!DNL PAServer.cfg] 作進行設定和儲存。

1. 定義 **[!UICONTROL Log Source ID]**.

   新增 **[!UICONTROL Recording of Rows per Log Source]** 至自訂 **[!UICONTROL v6.04]** 描述檔的檔案中，並在 [!DNL Log Processing.cfg] 其中定義唯一名稱的檔案 **[!UICONTROL Log Source ID]**。

   ```
   Log Processing.cfg
   Log Source ID = string: <Name your ID Here>
   ```

   如果您未定義記錄來源ID，則會出現下列錯誤：

   ```
   Missing Log Source ID in log processing.cfg.  
   Log Source ID must be defined for all log sources.
   ```

1. 由於已 [!DNL EventMessages.dll] 經更新，因此必須先註銷，然後跨群集 **[!UICONTROL Adobe Insight Server]** 註冊。

   * [!DNL InsightServer64.exe /unregserver]
   * [!DNL InsightServer64.exe /regserver]

1. 啟動群 **[!UICONTROL Adobe Insight Server]** 集中的服務。

伺服器安裝現已完成。

## 報告伺服器升級 {#section-afd9560a446242e9b06490e5f98aaaec}

>[!IMPORTANT]
>
>在升級至之 **[!UICONTROL Report Server v6.1]**&#x200B;前，您必須先升級至 **[!UICONTROL Server v6.1]**。

1. 使用描 **[!UICONTROL Software and Docs]** 述檔，從 **[!UICONTROL v6.1]** 套件下 **[!UICONTROL Report Server]** 載至本機資料夾。
1. 從下 **[!UICONTROL Report Server 6.1]** 載的套件複製並取代描述檔套件。

   >[!NOTE]
   >
   >檔案 [!DNL Insight.zbin] 夾中的文 [!DNL install] 件是用於本地化的備份檔案，必須存在於目 [!DNL install] 錄中。 根據啟動時 [!DNL .zbin] 傳遞的命令列設定，將使用此檔案或其他檔案。

1. （可選）修改報表伺服器設定檔案以支援雙位元組字元。

   資料工作台目前支援英文(-en-us)和中文(-zh-cn)。 您必須設定字型以支援單位元組和雙位元組字元：

   ```
   Report Server.cfg - Add Fonts 
      Fonts = vector: 2 items  
      0 = string: SimSun  
      1 = string: Arial 
   ```

   Windows作業系統也必須安裝所列的字型。

1. 設定 [!DNL Report Server v6.1].

   1. 停止服 **[!UICONTROL Adobe Insight Report Server]** 務。
   1. 以「管理員」身份啟動命令提示符。
   1. 導覽至「報表伺服器」 [!DNL install] 檔案夾。
   1. 使用下列命令刪除報表伺服器服務：

      ```
      ReportServer.exe /unregserver
      ```

1. 根據語言設定啟動服務：

   ```
   ReportServer.exe -RegServer -Locale -en-us (English) 
   ReportServer.exe -RegServer -Locale -zh-cn (Simplified Chinese)
   ```

1. 若要驗證報表伺服器是否以正確的設定執行，請開啟並 **[!UICONTROL Windows Service Manager]** 按一下滑鼠右鍵 **[!UICONTROL Adobe Insight Report Server - Properties]**。 執行檔的路徑將顯示更新的命令行設定。

報表伺服器安裝現已完成。

## 用戶端升級 {#section-c896e57ecd2847afb18f4d8ef7cc0e06}

>[!IMPORTANT]
>
>在升級至之 **[!UICONTROL Client v6.1]**&#x200B;前，管理員必須先升級至 **[!UICONTROL Server v6.1.]**

1. 啟動 [!DNL Insight.exe] 但請勿連線至任何描述檔。
1. 編輯檔 [!DNL Insight.cfg] 案，不會自動更新軟體。

   ```
   Update Software = bool: false
   ```

1. 連線至 **[!UICONTROL Software and Docs]** 個人檔案(softdocs)。
1. 下載 [!DNL Software\Insight Client\v6.10].
1. （可選）修改 [!DNL insight.cfg] 以支援雙位元組字元。

   資料工作台目前支援英文和簡體中文。 選擇字型以支援這兩種語言：

   ```
   Fonts = vector: 2 items  
   0 = string: SimSun 
   1 = string: Arial
   ```

1. 退出客戶端。
1. 將下載的 **v6.1客戶端包中的檔案複製** 到資料夾 [!DNL Install] 中。

   >[!NOTE]
   >
   >安 [!DNL Insight.zbin] 裝資料夾中的檔案是用於本地化的備份檔案，必須存在於安裝目錄中。 根據啟動時 [!DNL .zbin] 傳遞的命令列設定，將使用此檔案或其他檔案。
   >
   >例如，要啟動「簡體中文」，請建立命令行設定中傳遞的快捷方式。
   >
   >```
   >Insight.exe -zh-cn
   >```
   >
   >如果您要以英文（預設）啟動，則不需要變更命令列。

1. 啟動 [!DNL Insight.exe] 英文版或您為其他語言建立的捷徑。
1. 連線至您的設定檔，並允許用戶端與伺服器同步。
1. （可選）若要使用IME，請對檔案進行下列 [!DNL Insight.cfg] 變更：

   ```
   Localized IME = bool: true
   ```

   輸入法編輯器(IME)可讓您輸入國際字元。

1. （可選）編輯檔 [!DNL Insight.cfg] 案以自動更新軟體：

   ```
   Update Software = bool: true
   ```

   請參閱實作IME的指示。
1. 在配置檔案同步後重新啟動，以使用最新的 [!DNL .zbin] 檔案。

客戶機安裝現已完成。
