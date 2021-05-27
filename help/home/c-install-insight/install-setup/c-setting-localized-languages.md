---
description: 設定insight.zbin檔案以設定用戶端應用程式的語言。
title: 設定當地語系化語言
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# 設定當地語系化語言{#setting-up-localized-languages}

設定insight.zbin檔案以設定用戶端應用程式的語言。

## 更新Data Workbench伺服器元件{#section-5d07a081befc4eaa8fdf7fea904e0d48}

管理員必須先完成以下任務才能更新這些伺服器元件：

1. **更新至Data Workbench伺服器6.x。** 您需要更新檔案，以更新Data Workbench伺服器以進行本地 [!DNL base\localization\*.zbin] 化。然後，此[!DNL insight.zbin]檔案將被複製到客戶端。

   [!DNL insight.zbin]檔案隨[!DNL insight.exe]檔案一併包含在安裝資料夾中。 如果您連線至未提供語言專屬[!DNL .zbin]檔案的伺服器，Data Workbench將繼續使用此檔案。

   備份[!DNL insight.zbin]檔案可以使用任何語言提供。 因此，如果您使用中文的Data Workbench並連線至不支援此語言的伺服器，則您的Data Workbench用戶端仍會使用中文，即使伺服器變更您的基本設定檔，並從[!DNL Base/Localization]資料夾移除您的[!DNL .zbin]檔案亦然。

1. **更新Data Workbench報表伺服器。** Data  [!DNL insight.zbin] Workbench報表伺服器根資料夾的預設為英文。管理員需要從更新的報表伺服器套件選取並複製[!DNL .zbin]檔案，並將其置於Data Workbench報表伺服器的根目錄中。 與客戶端一樣，報表伺服器也需要所選語言的正確參數，例如[!DNL Insight.exe -zh-cn]

   1. 停止報表伺服器服務。
   1. 從新的報告伺服器包複製[!DNL Localization]資料夾。
   1. 從[!DNL Localization]資料夾中，複製[!DNL Insight.zbin]檔案，並將其置於[!DNL Insight.exe]所在報表伺服器的根目錄中。

   1. 新增任何必要引數，例如[!DNL insight.exe -zh-cn]
   1. 重新啟動報表伺服器。

## 更新Data Workbench用戶端{#section-9653d3fcaf2a4337a97b685857e7aeac}

更新伺服器後，請依照下列步驟更新每個用戶端。

1. 要確保在此更新期間客戶端未從伺服器進行更新，請將[!DNL Insight.cfg]參數設定為False。

   ```
   Update Software = bool: false
   ```

1. 重新啟動客戶端。
1. 導覽至「軟體」和「檔案」設定檔（SoftDocs設定檔），然後從用戶端套件下載所需的&#x200B;**[!UICONTROL insight.zbin]**&#x200B;檔案：[!DNL Software\Insight Client\Insight_6.1.zip]

1. 將[!DNL insight.zbin]檔案移至[!DNL insight.exe]所在的資料夾。

1. 要確保客戶端檔案現在從伺服器進行更新，請將[!DNL Insight.cfg]檔案參數更改為True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >您的客戶端將與伺服器同步，您將看到一條消息，指明它正在更新。 下載結束時，您會收到一條消息，詢問您是否要重新啟動客戶端。

1. 按一下&#x200B;**OK**&#x200B;重新啟動客戶端。

如果您收到下列訊息，表示[!DNL zbin]檔案未放置在與[!DNL Insight.exe]相同的位置。

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**本地化的閃屏**

Data Workbench會尋找下列閃屏檔案：

* 英文（預設）:[!DNL Base/Images/<version_product> Splash.png]
* 中文（從 — zh-cn開始）:[!DNL Base/Images/<version_product> Splash zh-cn.png]。

如果請求了閃屏，但缺少了閃屏，Data Workbench將預設訪問英文閃屏。

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
