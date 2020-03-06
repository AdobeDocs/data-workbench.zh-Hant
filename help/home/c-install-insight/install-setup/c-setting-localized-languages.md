---
description: 設定insight.zbin檔案，以設定用戶端應用程式的語言。
solution: Analytics
title: 設定本地化語言
topic: Data workbench
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 設定本地化語言{#setting-up-localized-languages}

設定insight.zbin檔案，以設定用戶端應用程式的語言。

## 更新資料工作台伺服器元件 {#section-5d07a081befc4eaa8fdf7fea904e0d48}

管理員必須先完成這些任務，才能更新這些伺服器元件：

1. **更新至資料工作台伺服器6.x。** 您需要更新檔案，以更新資料工作台伺服器以進行本地 [!DNL base\localization\*.zbin] 化。 然後 [!DNL insight.zbin] 此檔案將被複製到客戶端。

   在安 [!DNL insight.zbin] 裝資料夾中，檔案會與檔案一起 [!DNL insight.exe] 包含。 如果您連線至未提供特定語言檔案的伺服器，則資 [!DNL .zbin] 料工作台會繼續使用此檔案。

   備份文 [!DNL insight.zbin] 件可以以任何語言提供。 因此，如果您使用中文資料工作台並連線至不支援此語言的伺服器，則您的資料工作台用戶端仍會使用中文，即使伺服器變更了您的基本設定檔，並從資料夾移除您 [!DNL .zbin] 的檔 [!DNL Base/Localization] 案。

1. **更新資料工作台報表伺服器。** 資料 [!DNL insight.zbin] 工作台報表伺服器的根資料夾，預設會使用英文。 身為管理員，您必須從更新的報表伺服器套件中選 [!DNL .zbin] 取並複製檔案，並將它放置在資料工作台報表伺服器的根目錄中。 與用戶端一樣，報表伺服器也需要所選語言的適當引數，例如 [!DNL Insight.exe -zh-cn]

   1. 停止報告伺服器服務。
   1. 從新報 [!DNL Localization] 告伺服器套件複製資料夾。
   1. 從資 [!DNL Localization] 料夾中複製 [!DNL Insight.zbin] 檔案，並將它放置在報表伺服器的根目錄 [!DNL Insight.exe] 中。

   1. 添加任何必需引數，如 [!DNL insight.exe -zh-cn]
   1. 重新啟動報表伺服器。

## 更新資料工作台用戶端 {#section-9653d3fcaf2a4337a97b685857e7aeac}

更新伺服器後，請按照以下步驟更新每個客戶端。

1. 要確保客戶端在此更新期間未從伺服器獲得更新，請將引數 [!DNL Insight.cfg] 設定為False。

   ```
   Update Software = bool: false
   ```

1. 重新啟動客戶端。
1. 導覽至「軟體與檔案」描述檔（SoftDocs描述檔），並從用戶端套件 **[!UICONTROL insight.zbin]** 下載所需的檔案： [!DNL Software\Insight Client\Insight_6.1.zip]

1. 將檔案 [!DNL insight.zbin] 移至檔案夾所 [!DNL insight.exe] 在的位置。

1. 要確保客戶端檔案現在從伺服器進行更新，請將檔案引 [!DNL Insight.cfg] 數更改為True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >您的客戶端將與伺服器同步，您將看到一條消息，指出伺服器正在更新。 下載結束時，您會收到一則訊息，詢問您是否要重新啟動用戶端。

1. 按一下 **確定** ，重新啟動客戶機。

如果您收到下列訊息，表示檔 [!DNL zbin] 案未放置在與相同的位置 [!DNL Insight.exe]。

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**本地化的啟動顯示畫面**

資料工作台會尋找下列啟動顯示畫面檔案：

* 英文（預設）: [!DNL Base/Images/<version_product> Splash.png]
* 中文（當-zh-cn開頭時）: [!DNL Base/Images/<version_product> Splash zh-cn.png]。

如果請求啟動顯示畫面但遺失，資料工作台依預設會存取英文啟動顯示畫面。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

