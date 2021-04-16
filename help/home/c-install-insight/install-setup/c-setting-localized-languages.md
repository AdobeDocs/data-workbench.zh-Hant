---
description: 設定insight.zbin檔案以設定用戶端應用程式的語言。
title: 設定當地語系化語言
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 設定當地語系化語言{#setting-up-localized-languages}

設定insight.zbin檔案以設定用戶端應用程式的語言。

## 更新資料工作台伺服器元件{#section-5d07a081befc4eaa8fdf7fea904e0d48}

管理員必須先完成這些任務，才能更新這些伺服器元件：

1. **更新至資料工作台伺服器6.x。您** 需要更新檔案，以更新資料工作台伺服器以進行本 [!DNL base\localization\*.zbin] 地化。然後，此[!DNL insight.zbin]檔案將被複製到客戶端。

   [!DNL insight.zbin]檔案隨附在安裝資料夾中。 [!DNL insight.exe]如果您連線至未提供特定語言[!DNL .zbin]檔案的伺服器，則資料工作台會繼續使用此檔案。

   備份[!DNL insight.zbin]檔案可以以任何語言提供。 因此，如果您使用中文資料工作台並連線至不支援此語言的伺服器，則您的資料工作台用戶端仍會使用中文，即使伺服器變更您的基本設定檔，並從[!DNL Base/Localization]資料夾移除您的[!DNL .zbin]檔案亦然。

1. **更新資料工作台報表伺服器。** 依預 [!DNL insight.zbin] 設，資料工作台報表伺服器的根資料夾位於英文。身為管理員，您必須從更新的報告伺服器套件中選取並複製[!DNL .zbin]檔案，並將它放置在資料工作台報告伺服器的根目錄中。 與客戶端一樣，報告伺服器也需要選定語言的適當引數，如[!DNL Insight.exe -zh-cn]

   1. 停止報告伺服器服務。
   1. 從新的報告伺服器包複製[!DNL Localization]資料夾。
   1. 從[!DNL Localization]資料夾複製[!DNL Insight.zbin]檔案，並將它放置在[!DNL Insight.exe]所在之報表伺服器的根目錄中。

   1. 添加任何必需的參數，如[!DNL insight.exe -zh-cn]
   1. 重新啟動報表伺服器。

## 更新資料工作台用戶端{#section-9653d3fcaf2a4337a97b685857e7aeac}

更新伺服器後，請按照以下步驟更新每個客戶端。

1. 要確保客戶端在此更新期間未從伺服器獲得更新，請將[!DNL Insight.cfg]參數設定為False。

   ```
   Update Software = bool: false
   ```

1. 重新啟動客戶端。
1. 導覽至「軟體與檔案」描述檔（SoftDocs描述檔），並從用戶端套件下載所需的&#x200B;**[!UICONTROL insight.zbin]**&#x200B;檔案：[!DNL Software\Insight Client\Insight_6.1.zip]

1. 將[!DNL insight.zbin]檔案移動到[!DNL insight.exe]所在的資料夾。

1. 要確保客戶端檔案現在從伺服器進行更新，請將[!DNL Insight.cfg]檔案參數更改為True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >您的客戶端將與伺服器同步，您將看到一條消息，指出伺服器正在更新。 下載結束時，您會收到一則訊息，詢問您是否要重新啟動用戶端。

1. 按一下&#x200B;**OK**&#x200B;重新啟動客戶機。

如果您收到下列訊息，表示[!DNL zbin]檔案未放置在與[!DNL Insight.exe]相同的位置。

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**本地化的啟動顯示畫面**

資料工作台會尋找下列啟動顯示畫面檔案：

* 英文（預設）:[!DNL Base/Images/<version_product> Splash.png]
* 中文（當-zh-cn開頭時）:[!DNL Base/Images/<version_product> Splash zh-cn.png]。

如果請求啟動顯示畫面但遺失，資料工作台依預設會存取英文啟動顯示畫面。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
