---
description: 設定insight.zbin檔案以設定用戶端應用程式的語言。
title: 設定當地語系化語言
uuid: 97baf281-32fd-4df0-81a6-c2c7126b053c
exl-id: 29624b3a-e26a-48a9-9dcc-21ba829c34d4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 設定當地語系化語言{#setting-up-localized-languages}

{{eol}}

設定insight.zbin檔案以設定用戶端應用程式的語言。

## 更新Data Workbench伺服器元件 {#section-5d07a081befc4eaa8fdf7fea904e0d48}

管理員必須先完成以下任務才能更新這些伺服器元件：

1. **更新至data workbench伺服器6.x。** 您需要更新Data Workbench伺服器以進行本地化，方法是 [!DNL base\localization\*.zbin] 檔案。 此 [!DNL insight.zbin] 然後，檔案將複製到用戶端。

   安 [!DNL insight.zbin] 檔案會隨附於 [!DNL insight.exe] 檔案。 如果您連接到未提供特定語言的伺服器 [!DNL .zbin] 檔案，則data workbench會繼續使用此檔案。

   備份 [!DNL insight.zbin] 檔案可以以任何語言提供。 因此，如果您使用中文的Data Workbench，並連線至不支援此語言的伺服器，則您的Data Workbench用戶端仍會使用中文，即使伺服器變更了您的基本設定檔並移除您的 [!DNL .zbin] 檔案 [!DNL Base/Localization] 檔案夾。

1. **更新Data Workbench報表伺服器。** 此 [!DNL insight.zbin] data workbench報表伺服器的根資料夾依預設會使用英文。 身為管理員，您必須選取並複製 [!DNL .zbin] 檔案，並將其置於data workbench報表伺服器的根目錄中。 與用戶端一樣，報表伺服器也需要所選語言的正確引數，例如 [!DNL Insight.exe -zh-cn]

   1. 停止報表伺服器服務。
   1. 複製 [!DNL Localization] 資料夾。
   1. 從 [!DNL Localization] 資料夾，複製 [!DNL Insight.zbin] 檔案，並將其置於報表伺服器的根目錄中， [!DNL Insight.exe] 中。

   1. 新增任何必要引數，例如 [!DNL insight.exe -zh-cn]
   1. 重新啟動報表伺服器。

## 更新Data Workbench用戶端 {#section-9653d3fcaf2a4337a97b685857e7aeac}

更新伺服器後，請依照下列步驟更新每個用戶端。

1. 要確保在此更新期間沒有從伺服器更新客戶端，請設定 [!DNL Insight.cfg] 引數設為False。

   ```
   Update Software = bool: false
   ```

1. 重新啟動客戶端。
1. 導覽至「軟體」和「檔案」設定檔（SoftDocs設定檔），然後下載所需的 **[!UICONTROL insight.zbin]** 來自客戶端包的檔案： [!DNL Software\Insight Client\Insight_6.1.zip]

1. 移動 [!DNL insight.zbin] 檔案到 [!DNL insight.exe] 中。

1. 若要確定用戶端檔案現在已從伺服器更新，請變更 [!DNL Insight.cfg] 檔案參數為True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >您的客戶端將與伺服器同步，您將看到一條消息，指明它正在更新。 下載結束時，您會收到一條消息，詢問您是否要重新啟動客戶端。

1. 按一下 **確定** 重新啟動客戶端。

如果您收到下列訊息，表示 [!DNL zbin] 檔案未放置在與 [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**本地化的閃屏**

Data Workbench會尋找下列閃屏檔案：

* 英文（預設）: [!DNL Base/Images/<version_product> Splash.png]
* 中文（從 — zh-cn開始）: [!DNL Base/Images/<version_product> Splash zh-cn.png].

如果請求了閃屏，但缺少了閃屏，Data Workbench將預設訪問英文閃屏。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
