---
description: 設定insight.zbin檔案以設定客戶端應用程式的語言。
title: 設定本地化語言insight.zbin
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# 設定當地語系化語言{#setting-up-localized-languages}

設定insight.zbin檔案以設定客戶端應用程式的語言。

## 更新資料工作台伺服器元件 {#section-5d07a081befc4eaa8fdf7fea904e0d48}

管理員必須首先完成以下任務以更新以下伺服器元件：

1. **更新到資料工作台伺服器6.x。** 您需要通過更新資料工作台伺服器以進行本地化 [!DNL base\localization\*.zbin] 的子菜單。 此 [!DNL insight.zbin] 檔案將被複製到客戶端。

   安 [!DNL insight.zbin] 檔案包含在安裝資料夾中 [!DNL insight.exe] 的子菜單。 如果連接到不提供特定語言的伺服器 [!DNL .zbin] 檔案，資料工作台將繼續使用此檔案。

   備份 [!DNL insight.zbin] 檔案可以以任何語言提供。 因此，如果您使用中文資料工作台並連接到不支援此語言的伺服器，則即使伺服器更改了您的基本配置檔案並刪除您的 [!DNL .zbin] 檔案 [!DNL Base/Localization] 的子菜單。

1. **更新資料工作台報表伺服器。** 的 [!DNL insight.zbin] 預設情況下，資料工作台報表伺服器的根資料夾將使用英文。 作為管理員，將要求您選擇和複製 [!DNL .zbin] 檔案，並將其置於資料工作台報表伺服器的根目錄中。 與客戶端一樣，報表伺服器也需要選定語言的正確參數，如 [!DNL Insight.exe -zh-cn]

   1. 停止報表伺服器服務。
   1. 複製 [!DNL Localization] 資料夾。
   1. 從 [!DNL Localization] 資料夾，複製 [!DNL Insight.zbin] 檔案，並將其放在報表伺服器的根目錄中 [!DNL Insight.exe] 的子菜單。

   1. 添加任何必需參數，如 [!DNL insight.exe -zh-cn]
   1. 重新啟動報表伺服器。

## 更新資料工作台客戶端 {#section-9653d3fcaf2a4337a97b685857e7aeac}

更新伺服器後，請按照以下步驟更新每個客戶端。

1. 要確保客戶端在此更新期間未從伺服器更新，請設定 [!DNL Insight.cfg] 參數為False。

   ```
   Update Software = bool: false
   ```

1. 重新啟動客戶端。
1. 導航到「軟體和文檔」配置檔案（SoftDocs配置檔案）並下載所需的 **[!UICONTROL insight.zbin]** 檔案： [!DNL Software\Insight Client\Insight_6.1.zip]

1. 移動 [!DNL insight.zbin] 檔案到資料夾 [!DNL insight.exe] 的子菜單。

1. 要確保客戶端檔案現在從伺服器更新，請更改 [!DNL Insight.cfg] 檔案參數為True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >您的客戶端將與伺服器同步，您將看到一條消息，指出伺服器正在更新。 下載結束時，您將收到一條消息，詢問是否要重新啟動客戶端。

1. 按一下 **確定** 以重新啟動客戶端。

如果您收到以下消息，則表示 [!DNL zbin] 檔案未放置在與 [!DNL Insight.exe]。

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**本地化閃屏**

Data workbench查找以下閃屏檔案：

* 英語（預設）: [!DNL Base/Images/<version_product> Splash.png]
* 中文（從 — zh-cn開始）: [!DNL Base/Images/<version_product> Splash zh-cn.png]。

如果請求閃屏但丟失，則預設情況下資料工作台將訪問英語閃屏。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
